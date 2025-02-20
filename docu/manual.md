# Poinz user manual

This page gives you an overview on the features and most common use cases.

## Table of Contents

* [The Board](#the-board)
* [Joining and leaving rooms](#joining-and-leaving-rooms)
  * [Joining a room](#joining-a-room)
  * [Leaving a room](#leaving-a-room)
  * [Removing other users from the room](#removing-other-users-from-the-room)
* [The Story Backlog](#the-story-backlog)
  * [Adding stories](#adding-stories)
  * [Importing stories](#importing-stories)
  * [Editing stories](#editing-stories)
  * [Trashing stories](#trashing-stories)
* [Estimating](#estimating)
  * [New Round](#new-round)
  * [Settle](#settle)
  * [Consensus](#consensus)
  * [Manually reveal estimates](#manually-reveal-estimates)
  * [Estimating with "Confidence Levels"](#estimating-with-confidence-levels)
* [Settings](#settings)
  * [User Settings](#user-settings)
  * [Room Settings](#room-settings)
* [Security](#security)

## The Board

The board contains the [**Backlog**](#the-story-backlog) (list of stories on the left). The [**Estimation
Area**](#estimating), where we see all users in the room as well as the currently selected story (in the middle).
Optionally the [**Settings**](#settings) menu or the **Action Log** on the right.

![The Board](https://user-images.githubusercontent.com/1777143/153183459-f8e054c7-0d41-4119-9688-4c71a4af65fb.png)

## Joining and leaving rooms

### Joining a room

You can join a room in three different ways

1. Visit the [landing page](https://poinz.app) and click the big button **"Join new room"**. You will join a
   new room with a randomly assigned unique room id.

![Join Room Form](https://user-images.githubusercontent.com/1777143/97100613-89a28600-1695-11eb-9d03-94a482cc0678.png)

2. Visit the [landing page](https://poinz.app), **extend** the form and enter a custom room name, then hit Enter
   or click the join button. If the room with this custom name (the room id) already exists, you will join it. Otherwise
   a new room is created.

![Join Room Form extended](https://user-images.githubusercontent.com/1777143/152639158-54568b8d-a170-465e-bc29-bf81ced30b6c.png)

3. Join a room directly by visiting the room url. (e.g. https://poinz.app/test
   or  https://poinz.app/a-random-room-id-here). If the room with this name/id already exists, you will join
   it. Otherwise a new room is created.

Poinz will ask you for a username on your first visit. Afterwards your username is stored in the LocalStorage of your
browser and reused on subsequent joins.


### Leaving a room

You can leave a room by clicking the **leave** button in the top right corner. If you close your browser window or tab
while you are in a room, other users will see you as "disconnected".

![TopBar Quick Menu](https://user-images.githubusercontent.com/1777143/97100648-dd14d400-1695-11eb-88ac-53540c09608d.png)

![Disconnected Users](https://user-images.githubusercontent.com/1777143/97101301-94144e00-169c-11eb-9dc8-bfc5ed949c6a.png)

### Removing other users from the room

You can remove ("kick") other users from the room:

1. First click on the avatar of the user
2. Click on the **leave** button on the right to kick the user. 

(If you click outside of the avatar, the additional menu will be closed and the user stays in the room.)


![Kick User](https://user-images.githubusercontent.com/1777143/153208812-fe48231a-9fc3-4e73-b6a3-7114fb49a446.png)

## The Story Backlog

The story backlog contains all stories added or imported to your room. The story currently selected for estimation is
marked with a **orange bar** on the left.

### Adding stories

Simply fill in the form on the top left. The *Title* is mandatory, the *Description* is optional. Any url in the
description will be rendered as a clickable link.

You can also use markdown syntax in the story description. You can toggle between markdown and plaintext on the bottom right of the story description:

![Markdown support](https://user-images.githubusercontent.com/1777143/151653695-a5367261-a31c-4a21-871a-fcb93b0a30de.png)

### Importing stories

Drag and Drop a csv file with stories (e.g. an export from Jira) on to the backlog. The csv file should contain column
headers on the first line.

Example:

```
key,title,description
ISS-123,The Title, some Description
ISS-554,Another Story, With a description
```

Poinz will also parse a default **Jira** issue export, where column headers are named: "Issue Key", "Summary", "Description".

( Poinz uses [papaparse](https://www.papaparse.com/) to parse the given csv file.)

Note: If you want to link to your Issue Tracking System, check out [Issue Tracking URL](#issue-tracking-url).

### Editing stories

Hover a story in the backlog (or tap the story on your mobile device), in order to see a button with a **pencil** icon
on the top right. Click on the pencil to enter the edit mode. You can edit the title and the description of the story
and save or discard your changes.

![Edit Story](https://user-images.githubusercontent.com/1777143/97101051-3c74e300-169a-11eb-8fce-6d0495421229.png)
![Edit Story Form](https://user-images.githubusercontent.com/1777143/97101074-75ad5300-169a-11eb-96a0-d50ce8543040.png)

### Trashing stories

Hover a story in the backlog (or tap the story on your mobile device), in order to see a button with a **trash can**
icon on the top right. Click on the trash can to move the story to the trash. Switch to the list of trashed stories by
clicking on **Trash (N)** on the top of the Backlog. You can **restore** a trashed story or **delete it permanently**!

## Estimating

Only a single story can be estimated at a given time.

1. Click the story you want to estimate in the **Backlog** and click the blue **Estimate** button.
2. The board now shows the selected story. All users see the same story selected on the board. In the backlog, the
   selected story is marked with an orange border on the left.
3. Estimate the story by clicking one of the colored cards. By default the cards have the values ?, 1/2, 1, 2, 3, 5, 8,
   13, 21, 34, 55, BIG.
4. By default, the given estimates are *revealed* as soon as all active users did estimate. This behaviour can be
   changed in the settings (Auto Reveal).

### New Round

In many cases, your team does not "agree" on a value in the first round. It is recommended that you discuss and share
opinions before you start a new estimation round. You can start a new estimation round by clicking the blue **new
Round** button.

All previously given estimates on the currently selected story are **erased**, and your team can start voting again.

![new round](https://user-images.githubusercontent.com/1777143/97101245-0e909e00-169c-11eb-81f5-80a0c094014c.png)

### Settle

If you do not want to estimate until everybody voted for the same card, you can manually "settle" the estimation: Click
on one of the cards in the **Estimation Summary** to store that value on the story.

![estimation_summary](https://user-images.githubusercontent.com/1777143/133760536-117486ce-135f-41b0-b571-877ed992f914.png)

### Consensus

If all users estimated the same value, *consensus* is achieved, and the story will display a colored *badge*.

![consensus](https://user-images.githubusercontent.com/1777143/97101160-4ba86080-169b-11eb-997d-57b5648e6ff8.png)

### Manually reveal estimates

You can *reveal* the story at any time by clicking the blue **Reveal** button. Even if not all users in the room did
estimate. Poinz then displays all given estimates for this story (visible for all users).

![reveal](https://user-images.githubusercontent.com/1777143/97101241-08022680-169c-11eb-97de-9a27244c3dca.png)

### Numerical average and Recommendation

After the estimations are revealed, Poinz will display the numerical average (the sum of all estimated card values, divided by number of estimations) as well as a recommendation.

![recommendation](https://user-images.githubusercontent.com/1777143/190894580-4bc83999-d55e-44e7-805c-fa4954a3f305.png)

The recommendation is chosen as follows:

* The numerical average will always fall between two cards (except if consensus is achieved)
* The recommendation is either the higher of these two cards, or the lower one.
* Most of the time, **the higher card is chosen as recommendation** except, if the average is "really close" to the lower card (within 10% of the card value).

In the example shown, the lower card would be **13** the higher card is **21**. 21 is chosen as recommendation, since the numerical average of **19.5** is not within 10% of 13 ((19.5 - 13) > 0.1*13).
See [getEstimationSummary.js](/client/app/components/EstimationArea/getEstimationSummary.js); for the implementation.

### Estimating with "Confidence Levels"

You can enable the "Confidence" setting in your room to allow your colleagues to specify a confidence when estimating a
story.

If the feature is enabled, users will be able to select "Unsure" /  "Default" / "Very sure" when estimating a story:

![estimating_with_confidence](https://user-images.githubusercontent.com/1777143/135747987-de44939e-d90f-4ea4-8c05-f5820e3bbbbd.png)

After the story is revealed, the played cards are marked accordingly. In this example, Sergio did not specify his confidence (i.e. selected "Default"),
user ChromeU was very unsure about the story being "2", whereas Foxy was very sure, this story is "13"!

![estimating_with_confidence_revealed](https://user-images.githubusercontent.com/1777143/135748049-3be28220-17f6-490a-a80e-838d7390d67e.png)


### Estimation Matrix

The Estimation Matrix displays a table with all estimated stories (all stories with consensus), ordered by estimation value.
This allows you and your team members to estimate the current story in relation to other stories which improves your estimation results.

You can toggle between the Matrix and the Story via the small toggle bottom on the right, just below the users.

<img src="https://user-images.githubusercontent.com/1777143/151691920-496244fa-6395-4c8a-bc59-61c84d7cca5e.png" width="300" />



## Settings

### User Settings

These settings will affect your user.

![User settings](https://user-images.githubusercontent.com/1777143/153183453-eb20dfb7-df10-4ff3-885c-92a3fa700e6a.png)

#### Avatar and Email

Choose an avatar to be displayed in the Estimation Area, visible for all users in the room. If you set an email address
that is registered with https://gravatar.com, the gravatar "Icon" will be used. This overrides any selected Poinz
avatar.

#### Spectator

If you mark yourself as "spectator", you exclude yourself from estimations and can no longer take part in estimating
stories. If auto reveal is enabled, Poinz will "ignore you" and reveal the story as soon as all other users did estimate
the current story. You can still modify the backlog and [settle](#settle). This is helpful for Scrum Masters /
moderators.

You can also mark others as "spectator" by clicking on their avatar and then clicking the eye icon.

### Room Settings

These settings will affect the room and thus all users in the same room.

![Room settings](https://user-images.githubusercontent.com/1777143/150672684-d3eed4d0-c362-425f-a891-5cc45bab07be.png)

#### Auto Reveal

By default, Poinz will reveal the current story automatically (all given estimation values are shown) as soon as all
users in the room did estimate the current story. **Excluded** (spectators) and **Disconnected** users are ignored.

If this flag is removed, Poinz will not auto reveal and you can manually reveal the story.

#### Password Protection

By default, everybody can join your room. You can optionally set a password in order to protect unauthorized access to
your room.

**Setting a room password in an existing Room**

For an existing room without password protection, the room settings allow you to set a new password.
You can of course also override or remove an existing password.

![Room settings password protection not set](https://user-images.githubusercontent.com/1777143/152639068-ca609d73-b0cb-4302-a6b8-dd5d4db65075.png)
![Room settings password protection set](https://user-images.githubusercontent.com/1777143/152639067-14d27f6e-e736-4528-8d9b-821860fa6c94.png)

On all subsequent joins to a password protected room, the user is prompted with a password form:

![Password form](https://user-images.githubusercontent.com/1777143/152639234-19a06a04-93c5-4a5e-ab2a-ffc74f6b6ab9.png)

#### Confidence

If activated, users can specify whether they are unsure (not confident) or very sure (very confident) when estimating a
story. See [Estimating with "Confidence Levels"](#estimating-with-confidence-levels).

#### Custom Cards

![Custom cards](https://user-images.githubusercontent.com/1777143/98459768-238e2680-219e-11eb-9c05-c8d734fe2c81.png)

If the default set of cards does not meet your needs, you can change it.

* Label (first column) can be any string
* Value (second column) must be a number. Make sure that the values are unique
* Color (thrid column) can be any css valid color string (hex, rgb, named)

You can also use the text editor and edit the json array directly.

If you click on "Default", you immediately restore the default card configuration.

#### Issue Tracking URL

![Room settings issue tracking](https://user-images.githubusercontent.com/1777143/150672743-742c01e2-7b1b-4fb7-9ba4-3321901ead76.png)

If you want to link your imported stories to your Issue Tracking (e.g. Jira), you can set a URL here. E.g. *https://my.jira.com/browse/{ISSUE}*.
The placeholder {ISSUE} will be replaced with the issue key.

If you [import stories](#importing-stories) (via csv) Poinz will add a deeplink to the respective issue description.


## Security

By default, everybody that knows the name/ID of your room can join your room, without further authorization.

> :exclamation: **This means, anonymous people can read, modify and delete your stories as soon as they know the room ID.** :exclamation:

This is by design. When we created Poinz, we wanted a most simple solution, without the hassle of registration and user
management.

However, you might want to protect your data in some way. See ["Password Protection"](#password-protection) for more
information.

:warning: At any time, you are using Poinz at your own risk! Be aware that all information that you enter is potentially publicly available!
We do not recommend that you use Poinz as a permanent information storage. Poinz is provided as is, without warranty of any kind! :warning:
