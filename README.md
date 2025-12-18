# 

# **Quickstart**

Get up and running on the latest version of HubSpot’s developer platform.

Get started with app development by building and deploying a simple boilerplate app.

If you don’t have a developer account yet, click [<u>here</u>](https://app.hubspot.com/signup-hubspot/crm?intent=developer&uuid=109bb778-9d45-4eb2-b164-f9e9a9f9b1f8) to create a new developer account. If you previously created a developer account prior to August 29, 2025, check out [<u>this guide</u>](https://developers.hubspot.com/docs/getting-started/convert-your-account-into-a-developer-crm-account) for details on opting into the new developer platform.

## [<u>​</u>](https://developers.hubspot.com/docs/getting-started/quickstart#set-up-your-local-environment)

## **Set up your local environment**

Before getting started, install the latest version of the [<u>HubSpot CLI</u>](https://developers.hubspot.com/docs/developer-tooling/local-development/hubspot-cli/install-the-cli). In a terminal window, run the following command:

npm install -g @hubspot/cli && hs init

The CLI needs to be version 7.6.0 or later.

- You can check which version of the CLI you have by running hs --version.
- If needed, you can run the command npm install -g @hubspot/cli@latest to update to the latest version of the HubSpot CLI.

The hs init command will create a CLI configuration file and authenticate your HubSpot account.

- Follow the prompts to generate a Personal Access Key in your account, then copy and paste it into the terminal to save your configuration.
- It’s recommended that you make this account your default in the CLI.
- You can run hs account auth at any time to authenticate a different HubSpot account.

## [<u>​</u>](https://developers.hubspot.com/docs/getting-started/quickstart#create-and-upload-a-project)

## **Create and upload a project**

1

Get started

With the CLI installed, run hs get-started to initialize your project.

hs get-started

2

Configure your project details

You’ll then be greeted with a welcome message, and you can begin setting up your project and app.

- Following the prompts, select App.

- Give your project a name.
- Set your project’s local directory (by default this will be your current working directory).
- Upload your project to HubSpot to initialize the first build and deploy.

- You’ll then be prompted to install dependencies and upload your project. Installing dependencies before uploading ensures a faster build of the included app card, and makes sure that your local development environment and production match. This step will add a package-lock.json file and Node modules directory to the project’s cards/ directory.
- Then, confirm that you want to upload your project to your account.

## [<u>​</u>](https://developers.hubspot.com/docs/getting-started/quickstart#install-and-preview-your-app)

## **Install and preview your app**

1

Install your app

After your project deploys, you’ll be prompted to navigate to your HubSpot account to walk through installing and previewing your app.

- In the terminal, confirm that you want to open your account. A browser window will open the project details page in HubSpot.
- On the project details page, click Install now to install the app. You’ll then be taken to the app install page.

- On the app install page, click Connect App to install the app in your account.
- A confirmation message will appear once the app successfully installs. You can then close the page or click return home.

At any time, you can return to the project details page either through the terminal or in HubSpot:

- In the terminal, run hs project open while in the local project directory.
- In HubSpot, navigate to Development in the main navigation bar, then locate your project under _Recently updated projects_ or through the left sidebar.

2

Start local development

With the project uploaded and installed, you can start the local development server to preview your app card.

- In the terminal, navigate into your project directory, then run hs project dev.

As of [<u>Google Chrome version 142</u>](https://developer.chrome.com/release-notes/142#local_network_access_restrictions), you will receive a one time time popup asking for [_app.hubspot.com_](http://app.hubspot.com) to access devices on your local network. Select Accept to enable local development for your apps.

You can also manage this setting in your Chrome settings by navigating to Settings \> Privacy & Security \> [app.hubspot.com](http://app.hubspot.com) \> Permissions \> Local network access.

- When prompted, select the account you want to test in.
  - To test in a developer test account within your production account (recommended), select Test on a developer test account.
  - Select an existing test account, or select Test on a new developer test account. Then, follow the prompts to install the app in the test account.

For more advanced testing, you can create [<u>configurable test accounts</u>](https://developers.hubspot.com/docs/developer-tooling/local-development/configurable-test-accounts), which can be assigned specific combinations of HubSpot subscription tiers to ensure feature compatibility.

- The local development server will then start, and the terminal will provide a link to view the local dev session in HubSpot. Follow the link to open the HubSpot local development page in your account.

3

Setup local development preview

Before you can preview the app card on the contact record, you’ll need to add your new card to the contact record view.

- On the local development page, click Setup preview. You’ll then be redirected to the contacts index page.

- Click the name of a contact record.
- At the top of the middle column of the contact record, click Customize.
- Click Default view.
- Select the tab that you want to add the card to. You can then hover over the location where you want to place the card and click the plus button. This can be adjusted at any time after initial setup.

- In the right sidebar, click the Card library tab. Then, click the Card types dropdown menu and select App to filter for app cards.
- Click Add card under the app card you created, then click the close button in the top right of the sidebar.
- In the top right, click Save and exit.

You’ll then be redirected back to the contact record, and the app card will display with a Developing locally tag to indicate that the local development server is waiting to detect local changes.

You will not need to repeat the preview setup steps moving forward, unless you want to change the position of the card or customize another CRM record view.

4

Continue local development

While the local development server runs, it will automatically pick up on any changes saved to the app card’s front-end React file. If you need to make changes to other file types, such as a .json configuration file, you’ll need to reupload the project and restart the local development server.

To test this out, make a change to the app card’s local .jsx React file, then save your change. For example, change the text within one of the Text [<u>components</u>](https://developers.hubspot.com/docs/apps/developer-platform/add-features/ui-extensibility/ui-components/standard-components/text).

import React from "react";

import { Text, Link, List } from "@hubspot/ui-extensions";

import { hubspot } from "@hubspot/ui-extensions";

hubspot.extend(() =\> \<Extension /\>);

const Extension = () =\> {

  return (

    \<\>

      \<Text\>

        Woohoo!

      \</Text\>

      \<List variant="unordered-styled"\>

        \<Link href="https://developers.hubspot.com/docs/platform/ui-components"\>

          📖 Explore our library of UI components

        \</Link\>

        \<Link href="https://ecosystem.hubspot.com/marketplace/apps/app-cards"\>

          📖 Look at the Marketplace collection of apps that contain app cards

        \</Link\>

        \<Link href="https://developers.hubspot.com/slack"\>

          ▶️ Connect with developers on #ui-extensions channel on developer

          Slack community

        \</Link\>

      \</List\>

    \</\>

  );

};

## [<u>​</u>](https://developers.hubspot.com/docs/getting-started/quickstart#next-steps)

## **Next steps**

Now that you’ve successfully deployed your quickstart app, check out the following resources to continue building on HubSpot’s developer platform:

- [<u>App configuration</u>](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/app-configuration)
- [<u>Manage apps in HubSpot</u>](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/manage-apps-in-hubspot)
- [<u>Create app cards</u>](https://developers.hubspot.com/docs/apps/developer-platform/add-features/ui-extensibility/app-cards/create-an-app-card)
- [<u>UI extension components</u>](https://developers.hubspot.com/docs/apps/developer-platform/add-features/ui-extensibility/ui-components/overview)