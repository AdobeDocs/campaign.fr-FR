---
product: Adobe Campaign
title: Intégration des SDK Campaign à votre application
description: Découvrez comment intégrer les SDK Campaign Android et iOS à votre application
version: v8
feature: Push
role: Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: eec769a09d59034dde59983bd0a53a4ac4fddde5
workflow-type: tm+mt
source-wordcount: '1569'
ht-degree: 32%

---

# Intégrer les SDK Campaign avec votre application {#integrate-campaign-sdk}

Utilisez les SDK Campaign pour iOS et Android pour faciliter l’intégration de votre application mobile dans la plateforme Adobe Campaign.

Les versions prises en charge pour Android et iOS, ainsi que les versions compatibles avec les SDK Campaign pour Campaign v8, sont répertoriées dans la [matrice de compatibilité](../start/compatibility-matrix.md#MobileSDK) .

>[!NOTE]
>
>En tant qu’administrateur de Campaign, vous pouvez télécharger les SDK Campaign à partir de la [distribution logicielle Experience Cloud](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). Pour plus d’informations, contactez [l’ Assistance clientèle Adobe](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).


## Déclarer les paramètres d’intégration {#declaring-integration-settings}

Afin d’intégrer le SDK Campaign dans l’application mobile, l’administrateur fonctionnel doit fournir au développeur les informations suivantes :

* **Une clé d&#39;intégration** permettant à la plateforme Adobe Campaign d&#39;identifier l&#39;application mobile.

   >[!NOTE]
   >
   >Cette clé d&#39;intégration est renseignée dans la console Adobe Campaign, dans l&#39;onglet **[!UICONTROL Informations]** du service dédié à l&#39;application mobile. Reportez-vous à la [documentation de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#creating-ios-app).

* **Une URL de tracking** correspondant à l&#39;adresse du serveur de tracking Adobe Campaign.
* **Une URL marketing** permettant de collecter les abonnements.

* **Sous Android** :

   ```sql
   Neolane.getInstance().setIntegrationKey("your Adobe mobile app integration key");
   Neolane.getInstance().setMarketingHost("https://yourMarketingHost:yourMarketingPort/");
   Neolane.getInstance().setTrackingHost("https://yourTrackingHost:yourTrackingPort/"); 
   ```

* **Sous iOS** :

   ```sql
   Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl setMarketingHost:strMktHost];
   [nl setTrackingHost:strTckHost];
   [nl setIntegrationKey:strIntegrationKey];
   ```

## Intégrer le SDK Android

Le SDK Android est une bibliothèque jar écrite dans JAVA. Il permet aux développeurs Android de s’intégrer à Adobe Campaign : enregistrez un nouvel appareil, liez l’appareil à un utilisateur, suivez le comportement, etc.

Dans cette section, découvrez comment utiliser le SDK Android dans une application Android en implémentant [Google Firebase Cloud Messaging (FCM)](https://firebase.google.com/docs/cloud-messaging/).

### Configuration de FCM

Pour utiliser la notification push sur Android, vous devez disposer d&#39;un compte FCM, configurer votre application Android pour recevoir la notification et lier votre application au compte FCM. Pour en savoir plus, consultez la [Documentation Google](https://firebase.google.com/docs/cloud-messaging/).

Reportez-vous à la [Documentation Google](https://firebase.google.com/docs/android/setup) pour ajouter Firebase à votre projet Android.

Découvrez comment implémenter FCM dans votre application dans la [documentation Google](https://firebase.google.com/docs/android/setup).

>[!NOTE]
>
> * N’oubliez pas de télécharger et d’ajouter google-services.json à votre projet.
   >
   > 
* `apiKey` doit correspondre au `projectKey` défini dans l’application mobile Adobe Campaign liée à cette application Android.


### Configuration du SDK Android

1. **Initialisation du SDK**

   Avant d’utiliser le SDK Android, vous devez l’initialiser. L’initialisation du SDK peut être effectuée dans la fonction `onCreate` d’une activité.

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       // initialize Campaign SDK
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       Neolane.getInstance().setIntegrationKey(settings.getString(YourApplicationActivity.APPUUID_NAME, YourApplicationActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(YourApplicationActivity.SOAPRT_NAME, YourApplicationActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(YourApplicationActivity.TRACKRT_NAME, YourApplicationActivity.DFT_TRACKRT));
       ...
   }
   ```

   La valeur `IntegrationKey` doit correspondre à la valeur &quot;IntegrationKey&quot; définie dans l’application mobile Adobe Campaign liée à cette application Android.

1. **Enregistrement du périphérique mobile sur le serveur Adobe Campaign**

   La fonction d&#39;enregistrement permet :

   * d&#39;envoyer l&#39;identifiant de notification ou push id (deviceToken pour iOS et registrationID pour Android) à Adobe Campaign.
   * de récupérer la clé de réconciliation ou userKey (par exemple l&#39;adresse email ou le numéro de compte)

   Vous devez enregistrer votre appareil dans Adobe Campaign, à l’initialisation de l’application ou lors d’une action de l’utilisateur. Vous pouvez le faire facilement à l’aide de la méthode `registerDevice`.

   ```sql
   public void onClick(View v)
   {
   SharedPreferences settings = this.context.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   EditText mailEdit = (EditText) this.context.findViewById(R.id.editText1);
   
   final String FCMRegistrationId = FirebaseInstanceId.getInstance().getToken();
   if (FCMRegistrationId != null)
       NeoTripActivity.registerOnNeolane(this.context, FCMRegistrationId, mailEdit.getText().toString());
   
   }
   ```

   YourApplicationActivity.java

   ```sql
   public static void registerOnNeolane(final Context ctx, String registrationId, String userKey)
   {
       NeolaneAsyncRunner neolaneAs = new NeolaneAsyncRunner(Neolane.getInstance());
       // Additional Subscription Parameters
       Map<String,Object> additionnalParam = new HashMap<String, Object>();
       additionnalParam.clear();
       SharedPreferences settings = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN1_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME1_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE1_NAME, ""));   
       }
       if (settings.getBoolean(YourApplicationActivity.SUBPARAMEN2_NAME, false))
       {
           additionnalParam.put(settings.getString(YourApplicationActivity.SUBPARAMNAME2_NAME, "") , settings.getString(YourApplicationActivity.SUBPARAMVALUE2_NAME, ""));   
       }
       if ( additionnalParam.isEmpty() )
       {
           additionnalParam = null;
       }
       // Campaign Registration
       neolaneAs.registerDevice(registrationId, userKey, additionnalParam, ctx, new RequestListener() {
       public void onComplete(String e, Object obj)
       {
           Intent upd = new Intent();
           upd.setAction(BROADCAST_NEWREGISTER_ACTION);
           ctx.sendBroadcast(upd);
       }
   
       public void onNeolaneException(NeolaneException e, Object obj)
       {
           sendErrorMsg(e.getErrorString());
       }
   
       public void onIOException(IOException e, Object obj)
       {
           sendErrorMsg(e.getMessage());
       }
   
       public void sendErrorMsg(String err)
       {
           SharedPreferences.Editor edit = ctx.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE).edit();
           edit.putBoolean(YourApplicationActivity.REGISTRATION_ERROR_NEOLANE_KEYNAME, true);
           edit.commit();
           Intent toast = new Intent();
           toast.setAction(BROADCAST_TOAST_DISPLAY_TEXT);
           toast.putExtra("text", "An error happened, please register again (" + err + ")");
           ctx.sendBroadcast(toast);
       }
       });
   }
   ```

1. **Notifier Campaign lorsque le jeton de périphérique mobile de l’utilisateur change**

   Nous vous conseillons d’utiliser la fonction `registerDevice` lors de l’appel de la fonction `onTokenRefresh` pour informer Adobe Campaign du changement du jeton de l’appareil mobile de l’utilisateur.

   Par exemple :

   YourApplicationFirebaseInstanceIDService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.util.Log;
   
   import com.google.firebase.iid.FirebaseInstanceId;
   import com.google.firebase.iid.FirebaseInstanceIdService;
   
   import static android.content.SharedPreferences.*;
   
   public class YourApplicationFirebaseInstanceIDService extends FirebaseInstanceIdService 
   {
       @Override
       public void onTokenRefresh() 
       {
       SharedPreferences settings = getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       if (!settings.getBoolean(YourApplicationActivity.USE_GCM, false))
           {
           String refreshedToken = FirebaseInstanceId.getInstance().getToken();
           String userKey = settings.getString(YourApplicationActivity.USERKEY_NAME, "");
           Editor edit = settings.edit();
           edit.putString(YourApplicationActivity.FCM_REGISTRATIONID_NAME, refreshedToken);
           edit.commit();
           YourApplicationActivity.registerOnNeolane(this, refreshedToken, userKey);
           }
       }
   }
   ```

1. **Configuration du service Firebase Messaging**

   Étendez le `FirebaseMessagingService` dans le rappel `onMessageReceived` pour recevoir les messages. Nous vous recommandons d’appeler la fonction `notifyReceive` lors de l’appel du rappel `onMessageReceived` afin de permettre le suivi de la réception des notifications sur l’appareil mobile. Dans Adobe Campaign, il s’agit de la notification **print** : cette fonction doit être appelée juste avant de demander au système d’exploitation d’afficher la notification.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService 
       {
       private static final String TAG = "MyFirebaseMsgService";
   
       @Override
       public void onMessageReceived(RemoteMessage message) 
           {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
           }
       }   
   ```

   Pour le SDK Campaign Android v1.1.1

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras)
   {
       if( message == null ) message = "No Content";
       if( title == null )   title = "No title";
       if( url == null )     url = "http://www.tripadvisor.fr";
       int iconId = R.drawable.notif_neotrip;
   
       // notify Adobe Campaign that a notification just arrived
       SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
       NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
       nas.notifyReceive(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
       public void onNeolaneException(NeolaneException arg0, Object arg1) {}
       public void onIOException(IOException arg0, Object arg1) {}
       public void onComplete(String arg0, Object arg1){}
       });
       if (yourApplication.isActivityVisible())
       {
       Log.i("INFO", "The application has the focus" );
       ...
       }
       else
       {
       // notification creation
       NotificationManager notificationManager = (NotificationManager) context.getSystemService(Context.NOTIFICATION_SERVICE);
       Notification notification;
   
       // Activity to start
       Intent notifIntent = new Intent(context.getApplicationContext(), NotificationActivity.class);
       notifIntent.putExtra("notificationText", message);
       notifIntent.putExtra(NotificationActivity.NOTIFICATION_URL_KEYNAME, url);
       notifIntent.putExtra("_dId", deliveryId);
       notifIntent.putExtra("_mId", messageId);
       notifIntent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
       PendingIntent contentIntent = PendingIntent.getActivity(context, 1, notifIntent, PendingIntent.FLAG_UPDATE_CURRENT);
   
       notification = new Notification.Builder(context)
               .setContentTitle(title)
               .setContentText(message)
               .setSmallIcon(iconId)
               .setContentIntent(contentIntent)
               .build();
   
       // launch the notification
       notification.flags |= Notification.FLAG_AUTO_CANCEL;
       notificationManager.notify(1234, notification);
       }
   }
   ```

1. **Suivi des ouvertures des messages de données**

   Pour les messages de données, vous pouvez suivre le moment où un utilisateur clique sur une notification pour l’ouvrir, à l’aide de la fonction `notifyOpening`. L&#39;activité de notification sera créée lorsque l&#39;utilisateur clique sur la notification (créée lors de l&#39;appel de fonction `onMessageReceived`)

   Pour le SDK Campaign Android v1.1.1

   ```sql
   public class NotificationActivity extends Activity {
       public void onCreate(Bundle savedBundle) {
           [...]
           Bundle extra = getIntent().getExtras();
           if (extra != null) {
               // reinit the Campaign sdk
               SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
               Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
               Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));               
               Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
               // Get the messageId and the deliveryId to perform tracking
               String deliveryId = extra.getString("_dId");
               String messageId = extra.getString("_mId");
   
               if (deliveryId != null && messageId != null) 
               {
                   try {
                   Neolane.getInstance().notifyOpening(messageId, Integer.valueOf(deliveryId));
                   } catch (NeolaneException e) {
                   // ...
                   } catch (IOException e) {
                   // ...
                   }
               }
           }
       }
   }
   ```

1. **Tracker les ouvertures et les clics sur les messages de notification**

   Pour les messages de notification, le suivi des ouvertures/clics doit être effectué avec la fonction `notifyOpening` au sein de l’activité de lancement de l’application, comme ci-dessous :

   ```sql
   /** Called when the activity is first created. */
   @Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
   
       SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
       // initialize Campaign SDK
       Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
       Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
       Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```

   >[!NOTE]
   >
   > Une gestion similaire doit être effectuée si l’utilisateur utilise l’option `click_action` dans l’activité ciblée.


1. **Réception du suivi des messages de données**

   Pour les messages de données, le suivi est reçu au niveau de l’appel `onMessageReceived`. La fonction &#39;notifyReceive&#39; doit être appelée.

   YourApplicationMessagingService.java

   ```sql
   package com.android.YourApplication;
   
   import android.content.Context;
   import android.content.SharedPreferences;
   import android.os.Bundle;
   import android.util.Log;
   
   import com.google.firebase.messaging.FirebaseMessagingService;
   import com.google.firebase.messaging.RemoteMessage;
   
   import java.util.Iterator;
   import java.util.Map;
   import java.util.Map.Entry;
   
   
   public class YourApplicationFirebaseMessagingService extends FirebaseMessagingService {
   private static final String TAG = "MyFirebaseMsgService";
   
   @Override
   public void onMessageReceived(RemoteMessage message) 
       {
           Log.d(TAG, "Receive message from: " + message.getFrom());
           Map<String,String> payloadData = message.getData();
           final Bundle extras = new Bundle();
           final Iterator<Entry<String, String>> iter = payloadData.entrySet().iterator();
           while(iter.hasNext())
           {
           final Entry<String, String>  entry =iter.next();
           extras.putString(entry.getKey(), entry.getValue());
           }
   
           SharedPreferences settings = this.getSharedPreferences(YourApplicationActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           String mesg = payloadData.get("_msg");
           String title = payloadData.get("title");
           String url = payloadData.get("url");
           String messageId = payloadData.get("_mId");
           String deliveryId = payloadData.get("_dId");
           YourApplicationActivity.handleNotification(this, mesg, title, url, messageId, deliveryId, extras);
       }
   }
   ```

   ```sql
   public static void handleNotification(Context context, String message, String title, String url, String messageId, String deliveryId, Bundle extras){
       .....
       .....
           // notify Campaign that a notification just arrived
           SharedPreferences settings = context.getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
               public void onNeolaneException(NeolaneException arg0, Object arg1) {}
               public void onIOException(IOException arg0, Object arg1) {}
               public void onComplete(String arg0, Object arg1){}
       });
   }
   ```

1. **Recevoir le tracking des messages de notification**

   Pour les messages de notification, la réception de tracking doit être paramétrée à deux niveaux :

   * `onMessageReceived` (application non en arrière-plan) : la mise en oeuvre a été effectuée dans la section précédente.
   * `onCreate` de l’activité de lancement (ou de l’activité ciblée si  `click_action`la fonction est utilisée). (Application non en arrière-plan).

   Elle doit être effectuée au même moment que le suivi des clics/ouvertures.

   ```sql
   /** Called when the activity is first created. */
       @Override
       public void onCreate(Bundle savedInstanceState)
       {
           super.onCreate(savedInstanceState);
   
           SharedPreferences settings = getSharedPreferences(NeoTripActivity.APPLICATION_PREF_NAME, Context.MODE_PRIVATE);
   
           // initialize Campaign SDK
           Neolane.getInstance().setIntegrationKey(settings.getString(NeoTripActivity.APPUUID_NAME, NeoTripActivity.DFT_APPUUID));
           Neolane.getInstance().setMarketingHost(settings.getString(NeoTripActivity.SOAPRT_NAME, NeoTripActivity.DFT_SOAPRT));
           Neolane.getInstance().setTrackingHost(settings.getString(NeoTripActivity.TRACKRT_NAME, NeoTripActivity.DFT_TRACKRT));
   ...
   ...
   ...
   
       // Manage opening/receive tracking of message notification
       Intent intent = getIntent();
       Bundle data = intent.getExtras();
       String messageId = null, deliveryId = null;
       if( data != null ) {
       if (data.containsKey("_mId")) messageId = data.get("_mId").toString();
       if (data.containsKey("_dId")) deliveryId = data.get("_dId").toString();
       if ( messageId != null && deliveryId != null) {
           Log.i(TAG, "Notify opening from backgroun click_action");
           NeolaneAsyncRunner nas = new NeolaneAsyncRunner(Neolane.getInstance());
           nas.notifyOpening(messageId, deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.open_track_ok));
           }
           });
           nas.notifyReceive(Integer.valueOf(messageId), deliveryId, new NeolaneAsyncRunner.RequestListener() {
           public void onNeolaneException(NeolaneException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_sdk_error) + arg0.getErrorCode());
           }
           public void onIOException(IOException arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_io_error) +  arg0.getLocalizedMessage());
           }
           public void onComplete(String arg0, Object arg1) {
               toastMessage( "error", getString(R.string.rec_track_ok));
           }
           });
       }
       }
   }
   ```


## Intégration du SDK iOS

1. **Enregistrement du périphérique mobile sur le serveur Adobe Campaign**

   La fonction d&#39;enregistrement permet :

   * d&#39;envoyer l&#39;identifiant de notification ou push id (deviceToken pour iOS et registrationID pour Android) à Adobe Campaign.
   * de récupérer la clé de réconciliation ou userKey (par exemple l&#39;adresse email ou le numéro de compte)

   ```sql
   // Callback called on successful registration to the APNs
    - (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken
   {
     // Pass the token to Adobe Campaign
     Neolane_SDK *nl = [Neolane_SDK getInstance];
     [nl registerDevice:tokenString:self.userKey:dic];
   }
   ```

1. **Activer la fonction de suivi**

   La fonction de tracking permet de tracker l&#39;activation des notifications (ouvertures).

   ```sql
   (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   if( launchOptions ) { // Retrieve notification parameters here ... // Track application opening Neolane_SDK
   *nl = [Neolane_SDK getInstance]; [nl track:launchOptions:NL_TRACK_CLICK]; } 
   ...  
   completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **Tracking des notifications silencieuses**

   iOS permet d&#39;envoyer des notifications silencieuses, des notifications ou des données qui seront directement envoyées à une application mobile sans les afficher. Adobe Campaign vous permet de les tracker.

   Pour tracker votre notification silencieuse, suivez l&#39;exemple ci-après.

   ```sql
   // AppDelegate.m
   ...
   ...
   #import "AppDelegate.h"
   #import "Neolane_SDK.h"
   ...
   ...
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler
   {
   NSLog(@"IN didReceiveRemoteNotification:fetchCompletionHandler");
   if (launchOptions) NSLog(@"IN launchOptions: %@", [launchOptions description]);
   NSLog(@"Application state: %ld", (long)application.applicationState);
   
   // Silent Notification (specific case, can use NL_TRACK_RECEIVE as the user does not have click/open the notification)
   if ([launchOptions[@"aps"][@"content-available"] intValue] == 1 )
       {
   NSLog(@"Silent Push Notification");
   ...  
   ...
   //Call receive tracking
           Neolane_SDK *nl = [Neolane_SDK getInstance];
   [nl track:launchOptions:NL_TRACK_RECEIVE];
   
   completionHandler(UIBackgroundFetchResultNoData); //Do not show notification
   return;
   }  
   ...
   ...
           completionHandler(UIBackgroundFetchResultNoData);
   }
   ```

1. **Configurer le statut d’enregistrement**

   Le protocole délégué vous permet d’obtenir le résultat de l’appel **registerDevice** et peut être utilisé pour savoir si une erreur s’est produite pendant l’enregistrement.

   Le prototype de **registerDeviceStatus** est le suivant :

   ```sql
   - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status:(NSString *) errorReason;
   ```

   * **Status** permet de déterminer si un enregistrement a été effectué avec succès ou si une erreur s&#39;est produite.

   * **ErrorReason** fournit des informations supplémentaires sur les erreurs qui se sont produites. Pour en savoir plus sur les erreurs disponibles et leur description, reportez-vous au tableau ci-dessous.


| Status | Description | ErrorReason |
| ---------------------------------------------------------- | ------------------------------------------------------ | ----------------------------------------- |
| ACCRegisterDeviceStatusSuccess | Succès de l&#39;enregistrement | EMPTY |
| ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty | Le nom d&#39;hôte du serveur marketing ACC est vide ou non défini. | EMPTY |
| ACCRegisterDeviceStatusFailureIntegrationKeyEmpty | La clé d&#39;intégration est vide ou non définie. | EMPTY |
| ACCRegisterDeviceStatusFailureConnectionIssue | Problème de connexion lié à ACC | Informations supplémentaires (dans la langue actuelle du système d&#39;exploitation) |
| ACCRegisterDeviceStatusFailureUnknownUUID | L&#39;UUID indiqué (clé d&#39;intégration) est inconnu. | EMPTY |
| ACCRegisterDeviceStatusFailureUnexpectedError | Une erreur inattendue a été retournée au serveur ACC. | Message d&#39;erreur retourné à ACC. |


{style=&quot;table-layout:auto&quot;}

    Le protocole **Neolane_SDKDelegate** et la définition du délégué **registerDeviceStatus** sont les suivants : 
    
    &quot;sql
    // Neolane_SDK.h
    // SDK Campaign
    ..
    ..
    // Enregistrer le statut du périphérique 
    Enumtypedef NS_ENUM(NSUInteger, ACCRegisterDeviceStatus) {
    ACCRegisterDeviceStatusSuccess, // Résistration 
    SucceedACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty, // Le nom d’hôte du serveur marketing Campaign est vide ou non 
    vide setACCRegisterDeviceStatusFailureIntegrationKeyEmpty, // La clé d&#39;intégration est vide ou non 
    setACCRegisterDeviceStatusFailureConnectionIssue // Problème de connexion avec Campaign, plus d&#39;informations dans 
    errorReasonACCRegisterDeviceStatusUnknownUUID, // L&#39;UID (clé d&#39;intégration) fourni 
    unknownACCRegisterDeviceStatusFailureUnpendingError // Erreur inattendue renvoyée par le serveur Campaign, plus d’informations dans errorReason
    };
    // définir le protocole du délégué registerDeviceStatus
    @protocol Neolane_SDKDelegate  &lt;nsobject>
    @optional
    - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status : (NSString *) errorReason;
    @end
    @interface Neolane_SDK: NSObject {
    }
    ...
    ...
    // délégué de registerDeviceStatus
    @property (non atomique, faible)  &lt;neolane_sdkdelegate> délégué d’id;
    ...
    ...
    @end
    &quot;
    
    Pour implémenter le délégué **registerDeviceStatus**, procédez comme suit :
    
    1. Mettez en oeuvre **setDelegate** lors de l’initialisation du SDK.
    
    &quot;sql
    // AppDelegate.m
    ...
    ...
    - (BOOL)application :(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
    {
    ...
    ...
    // Obtenir les 
    
    paramètres stockésNSUserDefaults *defaults = [NSUserDefaults standardUserDefaults];
    NSString *strMktHost = [defaulobjectForKey:@&quot;mktHost&quot;];
    NSString *strTckHost = [defaulobjectForKey:@&quot;tckHost&quot;];
    NSString *strIntegrationKey = [default objectForKey:@&quot;integrationKey&quot;];
    userKey = [default objectForKey:@&quot;userKey&quot;];
    
    // Configurer le SDK Campaign lors du premier 
    lancementNeolane_SDK *nl = [Neolane_SDK getInstance];
     nl setMarketingHost:strMktHost];
    [nl setTrackingHost:strTckHost];
    [nl setIntegrationKey:strIntegrationKey];
    [nl setDelegate:self]; // ICI
    ...
    ...
    }
    &quot;
    
    1. Ajoutez le protocole dans la **@interface** de votre classe.
    
    &quot;sql
    // AppDelegate.h
    
    #import  &lt;uikit>
    #import  &lt;corelocation>
    #import &quot;Neolane_SDK.h&quot;
    
    @class LandingPageViewController;
    
    @interface AppDelegate : UIResponder  &lt;uiapplicationdelegate> {
    CLLocationManager *locationManager;
    NSString *userKey;
    NSString *mktServerUrl;
    NSString *tckServerUrl;
    NSString *homeURL;
    NSString *LandingPageUrl;
     STimer *timer;
    }
    &quot;
    
    1. Implémentez le délégué dans **AppDelegate**.
    
    &quot;sql
    // AppDelegate.m
    
    #import &quot;AppDelegate.h&quot;
     #import &quot;Neolane_SDK.h&quot;
     #import &quot;LandingPageViewController.h&quot;
    #import &quot;RootViewController.h&quot;
    ...
    ...
    - (void) registerDeviceStatus: (ACCRegisterDeviceStatus) status : (NSString *) errorReason
    {
    NSLog(@&quot;registerStatus: %lu&quot;,status);
    
     if ( errorReason!= nil )
    NSLog(@&quot;errorReason: %@&quot;,errorReason);
    
    if( status == ACCRegisterDeviceStatusSuccess )
    {
    // Succès de l’enregistrement
    ...
    ..
    }
    else { // Une erreur s’est produite
    NSString *message;
    switch ( status ){
    case ACCRegisterDeviceStatusUnknownUUID:
    message = @&quot;Unkown IntegrationKey (UUID)&quot;;
    break;
    case ACCRegisterDeviceStatusFailureMarketingServerHostnameEmpty:
    message = @&quot;URL marketing non définie ou vide&quot;;
    break;
    case ACCRegisterDeviceStatusIntegrationKeyEmpty:
    message = @&quot;Integration Key not set or empty&quot;;
    break;
    case ACCRegisterDeviceFailureConnectionIssue:
    message = [NSString stringWithFormat:@&quot;%@ %@&quot;,@&quot;Problème de connexion :&quot;,errorReason];&lt;a222 1/>break;
    case ACCRegisterDeviceStatusFailureUnforecastError:
    default:
    message = [NSString stringWithFormat:@&quot;%@ %@&quot;,@&quot;Unpending Error&quot;,errorReason];
    break;
    }
    ...
    ...
    }
    }
    @end
    &quot;

    
## Variables {#variables}

Les variables permettent de définir le comportement de l&#39;application mobile après réception d&#39;une notification. Ces variables doivent être définies dans le code de l’application mobile et dans la console Adobe Campaign, dans l’onglet **[!UICONTROL Variables]** du service d’applications mobiles dédié.

[!DNL :arrow_upper_right:] En savoir plus dans la  **documentation de** Campaign Classic v7 sur les applications mobiles :  [Étapes de configuration pour ](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html) iOS [et Étapes de configuration pour Android](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=fr).

Vous trouverez ci-dessous un exemple de code qui permet à une application mobile de collecter toutes les variables ajoutées dans une notification. Dans notre exemple, nous utilisons la variable &quot;VAR&quot;.

* **Sous Android** :

   ```sql
   public void onReceive(Context context, Intent intent) {
        ...
       String event = intent.getStringExtra("VAR");
        ...
   }
   ```

* **Sous iOS** :

   ```sql
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
   {
       ....
       if( launchOptions )
       {
           // When application is not already launched, the notification data if any are stored in the key 'UIApplicationLaunchOptionsRemoteNotificationKey'
           NSDictionary *localLaunchOptions = [launchOptions objectForKey:@"UIApplicationLaunchOptionsRemoteNotificationKey"];
           if( localLaunchOptions )
           {
            ...
            [localLaunchOptions objectForKey:@"VAR"];
           ...
           }
      }
   }
   
   // Callback called when the application is already launched (whether the application is running foreground or background)
   - (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)launchOptions
   {
       if( launchOptions )
       {
        ...
           [launchOptions objectForKey:@"VAR"];
       }
   }
   ```

>[!CAUTION]
>
>Adobe recommande de choisir des noms de variables courts car la taille des notifications est limitée : 4 ko pour iOS et Android.

## Extension du service de notification {#notification-service-extension}

**Pour iOS**

Le média doit être téléchargé au niveau de l&#39;extension du service de notification.

```sql
#import "NotificationService.h"

@interface NotificationService ()

@property (nonatomic, strong) void (^contentHandler)(UNNotificationContent *contentToDeliver);
@property (nonatomic, strong) UNMutableNotificationContent *bestAttemptContent;

@end

@implementation NotificationService

- (void)didReceiveNotificationRequest:(UNNotificationRequest *)request withContentHandler:(void (^)(UNNotificationContent * _Nonnull))contentHandler {
    NSDictionary *userInfo = nil;
    NSString *url = nil;

    self.contentHandler = contentHandler;
    self.bestAttemptContent = [request.content mutableCopy];

    userInfo = request.content.userInfo;
    if ( userInfo != nil )
    {
        url = userInfo[@"mediaUrl"];  // Get the url of the media to download (Adobe Campaign additional variable)
    }
    ...
    // Perform the download to local storage
```

## Extension du contenu de notification {#notification-content-extension}

**Pour iOS**

A ce niveau, vous devez effectuer les opérations suivantes :

* Associer votre extension de contenu à la catégorie envoyée par Adobe Campaign :

   Si vous souhaitez que l&#39;application mobile affiche une image, définissez la valeur de la catégorie dans Adobe Campaign, par exemple &quot;image&quot;. Dans l&#39;application mobile, vous créez une extension de notification avec le paramètre **UNNotificationExtensionCategory** ayant pour valeur &quot;image&quot;. Lorsque la notification push est reçue sur l&#39;appareil, l&#39;extension est appelée selon la valeur de la catégorie définie.

* Définir le style de la notification

   Vous devez définir le style avec les widgets adéquats. Pour une image, c&#39;est le widget **UIImageView**.

* Afficher le contenu multimédia

   Vous devez ajouter du code pour alimenter le widget avec les données multimédia. Voici un exemple de code pour une image :

   ```sql
   #import "NotificationViewController.h"
   #import <UserNotifications/UserNotifications.h>
   #import <UserNotificationsUI/UserNotificationsUI.h>
   
   @interface NotificationViewController () <UNNotificationContentExtension>
   
   @property (strong, nonatomic) IBOutlet UIImageView *imageView;
   @property (strong, nonatomic) IBOutlet UILabel *notifContent;
   @property (strong, nonatomic) IBOutlet UILabel *label;
   
   @end
   
   @implementation NotificationViewController
   
   - (void)viewDidLoad {
       [super viewDidLoad];
       // Do any required interface initialization here.
   }
   
   - (void)didReceiveNotification:(UNNotification *)notification {
       self.label.text = notification.request.content.title;
       self.notifContent.text = notification.request.content.body;
       UNNotificationAttachment *attachment = [notification.request.content.attachments objectAtIndex:0];
       if ([attachment.URL startAccessingSecurityScopedResource])
       {
         NSData * imageData = [[NSData alloc] initWithContentsOfURL:attachment.URL];
         self.imageView.image =[UIImage imageWithData: imageData];
         [attachment.URL stopAccessingSecurityScopedResource];
       }
   }
   @end
   ```
