# Technology approach for Alcaeus

Alcaeus will be one of the first apps built using the Thunderbolt Framework.

It will be targeted at desktop and tablets, with usability in phone profile as well.

### Technology parts

- __Framework / UI__ -- To be implemented in Thunderbolt.  
The impact of this will be spread across TB development as well, since
this app is the proving ground for the framework.  Not really
relevant to try to estimate the time impact per se as a result. 
  But, if TB was established, I'd figure a total of 1 week for UI
  work.

- __AWS S3__ -- S3 Will be used for general user data storage and associated 
record persistence, as well as a public access for tracks to allow media streaming as mp3.
Should be pretty straightfoward, and we have prior PoC code (1 - 2 days)  

- __Audio Playback__ -- The audio player tag for HTML will work for our
Electron desktop.  Will need to find a corresponding Nativescript player
  to create a direct control for (There appears to be several, including [this one](https://market.nativescript.org/plugins/nativescript-audio-player/),
  although be prepared to add some UI elements to this for control.
  All tolled, allow (2 - 3 days)
  
- __User management__ -- Separate TA architecture doc needed to detail
how the user login, directory, and permissions schemes will work.
  (1 - 2 days for doc, with estimate for implementation to follow)
  
- __Notifications/Messaging__ -- communication being a key part of this app,
we need to implement a decent system for this to be detailed in a separate TA
  architecture doc (1 - 2 days).
  
- __Publishing__ -- This is a whole subsection that requires a separate
doc.  Also, review state of the art and partnering services.
  
- __DAW Plugins__ -- not envisioned for 1.0, but something to research for later.


