# Google Photos -- App for photos library album slideshow in Hubitat Dashboard

## Google pre-requisite setup

1. Login to the [Google API Console](https://console.developers.google.com/)
2. In the top menu bar, click the `Select a Project` drop-down. Select an existing Project that you want to use, or click `New Project` in the top-right.
   * If creating a new project, enter a name and optionally edit the project-id -- then click `Create`
3. On the Google Dashboard that loads, click `+ ENABLE APIS and SERVICES` at the top
4. Enter `Photos` in the search bar, then select the `Photos Library API`
5. Click `ENABLE` on the next screen
6. Select `Credentials` in the left-side pane, then click `+ CREATE CREDENTIALS` at the top, and select `OAuth client ID`
7. You may be prompted to `CONFIGURE CONSENT SCREEN`. If not, continue to step 8.
   * Select `External` users (this is the only option allowed unless you are part of a Google Workspace)
   * Enter App information, e.g.:
     * App name: Hubitat Photos App
     * User support email: your_email@gmail.com
     * Developer contact information: your_email@gmail.com
   * Click `Save & Continue` on each page
   * Once complete, go back and repeat step 6.
8. Select `Application type` == `Web application`
9. Enter a name for the client, e.g. `Hubitat`
10. Under `Authorized redirect URIs`, click `+ ADD URI` and enter: `https://cloud.hubitat.com/oauth/stateredirect`
11. Click `CREATE`
12. You will see the new entry under `OAuth 2.0 Client IDs` -- on the far-right, click the download icon to download the credentials as a JSON file.  This file will be referred to as `credentials.json` in all subsequent documentation.

## Hubitat Installation

1. On the Apps Code page, press the **New App** button
2. Paste the code for `photos-app.groovy` and press the **Save** button (or type Ctrl-S)
3. Press the **OAuth** button, then press **Enable OAuth in App**, then press the **Update** button.
4. On the Drivers Code page, press the **New Driver** button
5. Paste the code for `photos-device.groovy` and press the **Save** button (or type Ctrl-S)
6. On the Apps page press the **Add User App** button then click on **Google Photos** in the list of available apps.
7. Copy and paste the contents of your Oauth2 `credentials.json` file downloaded from GCP into the **Google credentials.json** input field

**_NOTE: Don't forget to press the Done button to make sure the app sticks around!_**

## Authorization

1. On the Apps page, click the link to **Google Photos**
2. Now that the previous steps are complete, you should now see a section: **Auth Link** - _Click this link to authorize with your Google Photos library._
3. Click on this link, and walk through the steps to authorize with Google. When complete, you will be redirected back to a basic page provided by this HE app.
4. Click the specified link to return to the App configuration page.
5. Click the **Refresh Albums List** button to populate the `Album to use` drop-down (this may take a few seconds)
6. Select the album you want to use for the slideshow in the `Album to use` drop-down (you may need to open the drop-down twice after step 5, to see updated data)
7. Enter your preferred image resolution (optional)
8. Click the **Load Photos from Album** button -- this retrieves the current set of IDs from google to use for the slideshow
9. A `Google Photos Device` entry was created in your HE Devices -- you can use the `image` attribute of this device in your dashboards to display photos from your selected Google Photos album.  It will update once a minute.