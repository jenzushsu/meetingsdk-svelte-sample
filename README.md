# Zoom Meeting SDK Svelte sample

This repo is a [Svelte](https://svelte.dev/) app generated via [Vite](https://vitejs.dev/) that uses the [Zoom Meeting SDK](https://developers.zoom.us/docs/meeting-sdk/web/) to start and join Zoom meetings and webinars.

![Zoom Meeting SDK Client View](/public/images/meetingsdk-web-client-view.gif)

## Installation

To get started, clone the repo:

`$ git clone https://github.com/zoom/meetingsdk-vuejs-sample.git`

## Setup

1. Once cloned, navigate to the `meetingsdk-svelte-sample` directory:

   `$ cd meetingsdk-svelte-sample`

1. Then install the dependencies:

   `$ npm install`

1. Open the `meetingsdk-svelte-sample` directory in your code editor.

1. Open the `src/components/HelloWorld.svelte` file, and enter values for the variables:


   | Variable                   | Description |
   | -----------------------|-------------|
   | authEndpoint          | Required, your Meeting SDK auth endpoint that securely generates a Meeting SDK JWT. [Get a Meeting SDK auth endpoint here.](https://github.com/zoom/meetingsdk-sample-signature-node.js) |
   | sdkKey                   | Required, your Zoom Meeting SDK Key or Client ID for Meeting SDK app type's created after February 11, 2023. [You can get yours here](https://developers.zoom.us/docs/meeting-sdk/developer-accounts/#get-meeting-sdk-credentials). |
   | meetingNumber                   | Required, the Zoom Meeting or webinar number. |
   | passWord                   | Optional, meeting password. Leave as empty string if the meeting does not require a password. |
   | role                   | Required, `0` to specify participant, `1` to specify host. |
   | userName                   | Required, a name for the user joining / starting the meeting / webinar. |
   | userEmail                   | Required for Webinar, optional for Meeting, required for meeting and webinar if [registration is required](https://support.zoom.us/hc/en-us/articles/360054446052-Managing-meeting-and-webinar-registration). The email of the user starting or joining the meeting / webinar. |
   | registrantToken            | Required if your [meeting](https://developers.zoom.us/docs/meeting-sdk/web/client-view/meetings/#join-meeting-with-registration-required) or [webinar](https://developers.zoom.us/docs/meeting-sdk/web/client-view/webinars/#join-webinar-with-registration-required) requires [registration](https://support.zoom.us/hc/en-us/articles/360054446052-Managing-meeting-and-webinar-registration). |
   | zakToken            | Required to start meetings or webinars on external Zoom user's behalf, the [authorized Zoom user's ZAK token](https://developers.zoom.us/docs/meeting-sdk/auth/#start-meetings-and-webinars-with-a-zoom-users-zak-token). The ZAK can also be used to join as an [authenticated participant](https://support.zoom.com/hc/en/article?id=zm_kb&sysparm_article=KB0063837). |
   | leaveUrl                   | Required for Client View, the url the user is taken to once the meeting is over. |

   Example:

   ```js
   var authEndpoint = 'http://localhost:4000'
   var sdkKey = 'abc123'
   var meetingNumber = '123456789'
   var passWord = ''
   var role = 0
   var userName = 'Svelte'
   var userEmail = ''
   var registrantToken = ''
   var zakToken = ''
   var leaveUrl = 'http://localhost:5173'
   ```

1. Save `HelloWorld.svelte`.

1. Run the app:

   `$ npm run dev`

## Usage

1. Navigate to http://localhost:5173 and click "Join Meeting".

   ### Client View

   ![Zoom Meeting SDK Client View](/public/images/meetingsdk-web-client-view.gif)

   Learn more about [Gallery View requirements](https://developers.zoom.us/docs/meeting-sdk/web/gallery-view/) and [see more product screenshots](https://developers.zoom.us/docs/meeting-sdk/web/gallery-view/#how-views-look-with-and-without-sharedarraybuffer).
