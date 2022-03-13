# G6: User Testing
## Overview
I decided to implement my project as a Discord Bot, since it automatically takes care of the distributed and highly interactive nature of my project. This was my first time making a Discord Bot. The main functionality I decided to focus on was to make the process of indicating a desire for support private and low effort. I focused on making a scaled-down version of my G4 storyboard flow possible. 
## Flow
This flow is roughly as follows:
Users can mark themselves as available or not. This determines whether or not they are notified when there are requests for urgent support
Ask for help, indicate whether it’s urgent or not, and provide an optional message
The bot sends a message to the requester only, giving them information on 911 and crisis lines
Bot posts on behalf of the requester, relaying their message, with their identity separate from the message
The person who requested support can close out their request if they no longer want support by clicking the message’s “remove” button, or someone else can offer help by clicking on the message’s “offer help” button
Once someone offers help the bot creates a private channel for them within the server and invites them both to it
The bot begins the conversation with a link to conversation guidelines
The bot also has a button that deletes the conversation
The requester and offerer can now chat within the server, privately
When they are done talking, they can delete the conversation
## Features
For my medium-fidelity prototype I implemented the following features, modified from my G4 submission. 

1. Provide scaffold for 1:1 conversation
1. Provide emergency crisis line information
1. Put Users in or remove them from “available” role to get notifications for urgent requests
1. Relay message when someone asks for help in #help channel. If urgent, ping “available”
1. Remove from #help channel (upon someone offering to help or user closes themselves)
1. Make new private channel for 1:1 conversations
1. Delete a 1:1 conversation
1. My code is on replit: https://replit.com/@ResearchStudy/capstone22
1. I tried connecting it to my GitHub repo for this class, but it wasn’t working for some reason. I didn’t make GitHub issues for this, I just kept track of my todos in a txt file. Since I took longer to do this assignment, I ended up implementing all of the functionalities I was planning to implement (from the scaled-down version of my project). 
## Screenshots:
![Screenshot from Discord of the bot sending a confirmation after the user has sent a request for help](/img/G6_1.jpg)
_Screenshot of results from a user changing their availability status, and the user sending a request for support. The bot responds to the request with a link to crisis line information and a preview of what the user’s message was._
![Screenshot from Discord of the message the bot sent on behalf of the user](/img/G6_2.jpg)
_Screenshot of the #help channel, a channel where only the bot can post and where requests for support appear. Since the request sent was urgent, @available was pinged. A request for support message has two buttons, one for the person who requested support to remove the message if they no longer need help, and the other for someone else to offer support. In both cases, once the button is clicked, the message disappears, so that people can easily see who is still looking for help._
![Screenshot from Discord of a 1 on 1 channel created by the bot](/img/G6_3.jpg)
_Screenshot of a 1-on-1 support channel, which gets created when someone clicks “offer help” under a request for support. Both the requester and offerer are pinged and the bot posts a link to conversation guidelines as well as a button for deleting the channel._
## Findings:
The main findings I got from the testing sessions were related to usability and the unintuitive nature of the server. At first I didn’t have any instructions on how to interact with the bot and what its available commands are. After finding out that was confusing, I added some simple instructions, but people didn’t bother reading them, so I need to find some way of conveying the available interactions. I also need to come up with better names for things and expose errors.

There isn’t an indication that someone’s request has been posted to #help, aside from if they’d previously read all the messages in that channel and now there’s a new unread message. I want to find some way to show that their message did get posted.

Also, if multiple people have requested help with no message, it’s pretty much impossible to tell which one belongs to you. I need to figure out a way to identify messages in #help but only to the person who requested support.

I realized I didn’t want people writing in #start-here or #help, to minimize clutter. 

The last main thing was that the big button to delete the channel was too tempting to click on immediately. I have to figure out a way to make it not so easy to click.

One thing I wanted to implement but didn’t get around to yet is the deletion of a 1-on-1 channel. I wanted to make the button so it would make a user leave the channel rather than deleting it. However, I couldn’t get that code working in time. The main goal with leaving/deleting would be so that unused channels don’t accumulate. Deleting a channel isn’t ideal in case someone (particularly, the person who requested help) wants to keep its history. Also, being able to abruptly delete 1-on-1 channels without the other person’s consent could be abused.

At this point, I don’t think I can make any drastic changes. I didn’t get signs that my bot is “promising” but that could just be due to the people I tested with not being the target audience (due to time constraints). I will make changes to address the findings from above, but probably won’t end up changing much else.
