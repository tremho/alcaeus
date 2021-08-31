

# Sign in

Sign-in / Sign-up will be done using OAuth providers 

- Apple 
- Google
- Facebook

No user/password recording will be done.  However, I am considering a creating a white-label OAuth service.

## First TODO: Read up on each of these

[Sign-in with Apple](https://developer.apple.com/sign-in-with-apple/get-started/)
[Sign-in with Google](https://developers.google.com/identity/sign-in/web/sign-in)
[Continue with Facebook](https://developers.facebook.com/docs/facebook-login/)

I am assuming at this point that these are all variations on a theme, although I suspect the Apple feature set is the most enviable.

I am also assuming I have a basic idea of how this works:
- user picks one and gets verified by the provider.  This might be by cookie or by biometric id, or by a user/password sign-in.  In any of these scenarios,
we have to be able to surrender control to their web experience.

- we get called back on the listening mechanism (this used to literally be a port, but times have updated things.  I think this can happen with an async web
request these days.  I think what we had done at INRIX was an AWS service listener for this purpose).

Assuming this is still the case, here is the flow:

- Prior to contacting the SSO, send an id token to our listening service so it knows we are expecting a login.
- do the SSO thing. it will call back to the listening service with the auth tokens and reference our id, so we can keep this safe (for a limited time)
- once we know this has been done, we can ask the listening service for our token by id.
- once delivered, the listening service can flush it.
- at this point, we have a validated token. this token can be used for SSO-supplied APIs.
- we may need to call the SSO provider to get user info, or it may come as part of the token delivery.  all we need is a stable user ID.
- we can use that ID in our own database to link to the account. we already know that this ID is verified as the actual user.

- that's it.  but within our own account management we still have to keep track of access permissions, et. al. and of course are sill bound by
any privacy disclosure or other security breach concerns.

#### Requirement wish-list
If you sign in with one, and your account is associated with that userID then you sign in with another, it should still work.
- record the provider name (id) along with the token so you know if you are comparing apples to apples
- on first ever sign-in, we sign-up, and collect information about the user (email, username, musician info, etc.)
- if never signed in with the alt-service before, ask questions that will validate. Once cleared in this manner, alert the user by email.
  - _(because a legitimate FB guy could pretend to be you, and if he knows the answer, become you)_
- if the 'free to switch providers' option is not viable:
  - on subsequnt logins, drop the other options from display.
  - in account settings, allow a new 'sign-up choice' to select a new provider.  
  
I'm not a security guy (at least not as of this writing), so I'm not sure what to do here.  But I think option #2 is the more responsible option even though
it sucks a bit in useability.

###### pitfalls to that
If you can't login anymore with your selected provider (you forgot your credentials/you were hacked/service is down), you are screwed unless you can try anotehr option.

- if we sign in with other providers while signed in with one, we can validate this.  So maybe have a user flow that invites them to sign in with any providers they think
they might use, and then jettison the rest.  Again, have an option in account settings that allows us to pick up these 'ignored' ones later if we want (once signed in).

- and then no allowance beyond on-boarded SSOs.


### First shared module

This will be the first step for both Alcaeus and Prepared (for Dinner) so it needs to be solid and portable.  It can probably become a Jove standard once matured.

- will need to be sure layout + CSS is set up to be flexible enough for a wide variety of cases.
- bone simple API.
- built-in Telemetry option. Look for evil doers.

