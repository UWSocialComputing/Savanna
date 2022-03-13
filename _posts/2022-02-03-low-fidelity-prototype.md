# G3: Low Fidelity Prototype
## Overall explanation of the system
The system I’ve made a low-fidelity prototype for is an app for making it easier to reach out to friends or strangers for help in time of mental health need and to make it easier to offer help to those who need it. The idea is to use a status indicator to show when someone is looking for help and to show when someone has the capacity to help. Then, when there is visibility on both sides, people looking for help can reach out and ask for it from others who want to talk and people who are looking to help others can reach out to people who want someone to talk to.

The first draft of the status indicator goes across two main dimensions: mood and availability. Here is a diagram showing them:

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G3_1.png?raw=true" alt="diagram showing faces of varying emotions, with an arrow labeled A going from a happy to a sad face and an arrow labeled B going between two sad faces"/></div>

The goal of this system is to facilitate more of relationship A and relationship B. In relationship A, people who are feeling okay and are willing to talk and people who are experiencing mental health issues and are wanting to talk can support each other. In relationship B, people who are experiencing mental health issues and are wanting to talk can find and confide in each other. A third dimension that can be adjusted is whether to share one’s mental health status with friends, strangers, both, or neither.

## Description of the low-fidelity prototype
My low fidelity prototype consists of an app and a widget. The widget is used for two main purposes: for someone to adjust their status and for someone to see which of their friends are experiencing mental health issues. In addition to the dimensions described above, the status adjustment includes options for adding tags for topics that the person is looking for help with or wants to talk about.

The app is used for finding people to engage in conversation with. There is a “public” mode, where people can see the mental health statuses of anonymous strangers and a “friends” mode, where people can see the mental health statuses of their friends. People can either message strangers through the app anonymously or have quick access to existing platforms they already use to chat with their friends. The app also includes settings and a way to add other users to the “friends” category.

For the low-fidelity prototype all parts were wizardry. I used Figma to create the prototype and the various buttons were “usable” by using Figma’s prototyping tool. Due to the specificity and custom-ness of the status indicator, at this point there wasn’t anything I could easily implement or piggyback on an existing platform, so all the elements were wizard-ed. 
## Selected images from the prototype
Here are some images of the important parts of the prototype. 

First is the widget. On this screen, the user can pick their mood by tapping one of the five faces. They can add tags by entering comma-separated words into the text entry box. They can indicate whether they want to talk to someone or would rather be left alone, or are somewhere in between by tapping the green, yellow, or red circles. They can tap the toggles to choose whether they want to make their new status visible to friends and whether they want to make it visible to strangers. The choices are automatically saved. The bottom section of this screen is where users can see how many of their friends are distressed/very distressed and wanting to talk.

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G3_2.png?raw=true" alt="screenshot of a protytype showing an interface for updating status"/></div>

The next screen is the “public” mode of finding someone to talk to. Here users see a list of people who have indicated they are wanting/willing to talk to someone, ordered by when their status was last updated. Users can see each person’s mood, their anonymous id (copied from Google’s way of anonymizing users), the last update of their status, and the tags the person has entered in their status. Users can also browse the people who indicated they kind of don’t want to talk, but this is collapsed by default. At the top of the screen users can choose to see all other strangers who have made their statuses publicly visible, or can filter and find people with the same mood, those who are “looking”, and those who are “offering”. The terms “looking” and “offering” are copied from a subreddit and Discord community called r/KindVoice that I have been taking inspiration from for this project. In this case, those who are distressed or very distressed and who are wanting to talk to someone would be considered “looking”, and those who are feeling better than neutral and who are willing to talk would be considered “offering”. By clicking on an avatar users can view a stranger’s profile and message them.

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G3_3.png?raw=true" alt="screenshot of a protytype showing an interface for viewing the statuses of strangers"/></div>

This screen is the view of a stranger’s profile. Here a user can see the same information about someone as the previous page, with the addition of seeing any profile information someone has added, such as topics they’re experienced in or are wanting/willing to talk about. At the bottom of the screen users can send a message to reach out to this person if they want to ask for help from this person or offer help to this person.

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G3_4.png?raw=true" alt="screenshot of a protytype showing an interface for viewing a stranger's profile"/></div>


This screen is the “friends” view of finding someone to talk to. Here users can see their friends who are wanting or willing to talk, again with the yellow “kind of don’t want to talk” and the red “leave me alone” statuses collapsed by default. In this view users can only see their friends’ mood and willingness to talk. Users can click on any of their friends to get to their profile screen.

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G3_5.png?raw=true" alt="screenshot of a protytype showing an interface for viewing friends' statuses"/></div>

A friend’s profile screen is pretty simple and only shows their mood, willingness to talk, name, and preferred contact methods. Since they’re friends already, the user would contact this person by just tapping one of the preferred contact methods, which would open up the respective communication platform.

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G3_6.png?raw=true" alt="screenshot of a protytype showing an interface for seeing a specific friend's contact information"/></div>

## Findings from the Wizard of Oz testing

I came into the Wizard of Oz session hoping to learn:
- People’s thoughts on the level of expression allowed by the status indicator
- People’s thoughts on the amount of information displayed about others
- How people feel about the public and friends modes
- Whether people would actually use this
- How to get people to keep their statuses up-to-date

I got a lot of useful feedback from the session. I’ll note just a few of the big ideas here. 
- The fact that the same widget is used to indicate wanting help and offering help was confusing
- The time aspect (for example, “20 min ago”) of the public statuses was confusing, but would be useful if implemented well
- It’s comforting to know that others are also feeling down
- I need to be careful to not create “another Instagram” where people display themselves as happy even when they’re not 
- Something to watch out for is people assuming other friends are “taking care of it” if they see a lot of happy friends willing to talk and not many friends in distress
- I need to design this such that people know where to draw the line between helping others and referring them to a professional so that people are comfortable using this
- Implement daily push notifications reminding people to update their statuses

Based on the feedback, I’ll move forward with implementing something that serves the same purpose as my current design, but with some changes. I have to think about the feedback to figure out how big those changes might be. I think I’ll keep the main idea of status indicators and direct messaging and using tags to make the statuses more descriptive. The big revisions will be figuring out how to display others’ statuses in a useful way that encourages authentic and productive behavior and makes sure people are being redirected to professionals when needed, redesigning how statuses are updated (since people found that confusing), and switching from a widget to push notifications to make sure statuses are up-to-date.


