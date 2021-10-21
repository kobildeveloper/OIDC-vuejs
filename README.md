# mIdentityBox - Implicit Flow using VueJS

This repo contains VueJS example app that demonstrate the various OpenId Connect's Implicit flow.

## Instructions

1. Initially clone this Repository
2. RUN `npm install` and wait for the completion of installation on `node_modules`.
3. Once `node_modules` are installed and RUN `npm run serve` to start execution of `vue-cli-service serve`.
4. You will receive a localhost URL, open that specific URL in your browser to view your initial screen
5. You can configure your OIDC related information in ```src/model/Config.js``` path.
6. Make sure you replace `your-midentity-box-oidc-tenant-id` with your TenantID and `your-midentity-box-oidc-app-client-id` with your ClientID when you created your OpenId Connect app via mIdentity Box portal
7. Change `{partnerid}.{hostname}` to match the sub-domain by mIdentity Box portal.

**Note:** Check with mIdentity Box administrator to enable Implicit Flow

### Example

```
Available on:
You can now view midentitybox-implicitflow in the browser.

App running at:
  - Local:   http://localhost:8080/ 
  - Network: http://<IP>:8080/

  Note that the development build is not optimized.
  To create a production build, run npm run build.
```

## Approach to work with the implicit flow

1. Click on "login" button.
2. You will be redirected to "mIdentityBox" user authentication screen.
3. Complete all of the authentication steps.
4. Depending on the response type you configured, you will receive a token.

## What can I use these for

OpenID Connect is a perfect way to incorporate user authentication to your application, where you are relying on another party to handle user identity.

In this situation, Keycloak handles the identity of the users, allowing it faster to get up and running.

## Single Sign On (SSO)

By integrating OpenID Connect via Keycloak, you are building a session that can be used to single sign-on from your custom app to other applications that your users can access via the Keycloak portal.

If you have any queries/you find any problems, please don't hesitate to raise an issue.

## MFA
If MFA is enabled for a user in mIDentity Box then they will be prompted to enter a token during the authentication. mIDentity Box takes care of all of this for you, making strong authentication much easier to implement in your app.

## Requirements
In order to run any of the examples you will need to create an OpenId Connect app in mIDentity Box Admin portal.

### Mobile App
1. [Android app](https://play.google.com/store/apps/details?id=com.kobil.mIdentity.box)
2. [iOS App](https://apps.apple.com/us/app/midentity-box/id1534159545)


If you don't have a mIDentity Box account [you can sign up here](https://midentitybox.com/selfenrollment).