# Flutter WebView

A new Flutter WebView application.

## Getting Started

For help getting started with Flutter, view our online [documentation](https://flutter.dev/docs).


## How it works
        return Scaffold(
          appBar: AppBar(
          title: const Text('Git Hub'),
          // This drop down menu demonstrates that Flutter widgets can be shown over the web view.
      ),
      body: WebView(
        initialUrl: 'https://github.com',
        onWebViewCreated: (WebViewController webViewController) {
          _controller.complete(webViewController);
        },
      ),
    );

## Webview Functions
     WebView({
      Key key,
      this.onWebViewCreated,
      this.initialUrl,
      this.javascriptMode = JavascriptMode.disabled,
      this.javascriptChannels,
      this.navigationDelegate,
      this.gestureRecognizers,
      this.onPageStarted,
      this.onPageFinished,
      this.debuggingEnabled = false,
      this.gestureNavigationEnabled = false,
      this.userAgent,
      this.initialMediaPlaybackPolicy =
          AutoMediaPlaybackPolicy.require_user_action_for_all_media_types,
    })
    
 ## problem 
 
  Android throws an exception when view page the javascript isn't shown 
  
  ## solving 
  webview default  
  
        JavascriptMode.disabled,
        
  you need to add this WebView function
  
            javascriptMode:JavascriptMode.unrestricted,

  
 ## problem 
 
 when in debug mode everything looks good, get response and lists of data from my API. But after I build app-release.apk and install to   my phone, it shows no internet connection
 
 ## solving
 
  In the (AndroidManifest.xml) file located at <android/app/src/main> you need to add this permission in <manifest tag.
  
      <uses-permission android:name="android.permission.INTERNET"/>

  
 
