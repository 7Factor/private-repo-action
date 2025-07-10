# private-repo-action

An action for authenticating a workflow to access private repositories using a GitHub App.

## Why?

There are many reasons you may want to access a private repository in an organization through a workflow that lives
in a different repository in that organization. Unfortunately, GitHub has not provided any great mechanisms for making
this easy. The most straightforward approach is using a PAT. However, the PAT approach has problems we'd rather not
deal with. Primarily, it is associated with a single user. If that user is removed from the organization, the PAT will
have to be recreated. Additionally, the PAT may expire. Using a GitHub App is a viable alternative, as it does not have
either of those downsides. However, it is slightly more complicated to set up and use. This action is intended to make
using the GitHub App approach a bit easier.

## Setup

Before you can use this approach, you need to set up the app. Head over to your organization settings, and in the
Developer Settings go to GitHub Apps. Create a new app with whatever settings you like, but make sure to set up the
permissions like you would for the PAT to access your org's private repositories. Once the app is created, you will
also need to generate a Private Key. Store the App ID as a GitHub variable, and the Private Key as a GitHub secret;
You'll need those for this action.

## Usage
