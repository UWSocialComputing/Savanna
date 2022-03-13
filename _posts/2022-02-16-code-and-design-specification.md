# G4: Code and Design Specification
## Requirements

### Functional requirements: Users can…
#### Primary
- Ask the bot for tips when engaging in 1:1 conversation
- See all available Tags for using when updating status
- Request a new anonymous id for privacy
- Turn notifications for others looking for support on or off
- Clear their statuses once they no longer need help
- Update status to indicate they want support, which can trigger a ping to certain other Users or show up ambiently in a channel called Ambient that shows the statuses of Users currently looking for support
- See the list of other Users currently seeking help, and what is upsetting them (Tags)

#### Secondary
- Users can offer to help others
- Users can create a private channel and invite the person they’d like to help to it
- Users can be effectively matched by topic Tags–Users looking for help will only end up reaching out to Users who are comfortable with their specified Tags, and Users offering help won’t be bothered by irrelevant pings
- Users can make profiles with Tags showing topics they’re familiar with
- Users can look up other Users to see what topics they are comfortable talking about (either for reaching out for help or reaching out to help)

### Technical requirements: Bot should be able to…
#### Primary
- Provide scaffold for 1:1 conversation, including emergency crisis line information
- Provide a list of valid Tags to choose from
- Assign new anon id
- Put Users in “available” or “do not disturb” roles
- Clear User statuses
  - Remove from Ambient channel
  - Reset User status to default
- Update User statuses
  - If urgent and supported, ping “offering”
  - If urgent and mutual, ping “available”
  - (may make roles more granular at the Tag level, not sure yet)
  - If non urgent, post in Ambient channel
- Relay message and tags when someone asks for help in Ambient channel

#### Secondary
- Relay an offer to help to the person asking for it to Ambient
- Make new private channel for 1:1 conversations
- Bot DMs people to ask for help based on matching tags rather than pinging everyone in “offering”
- Update User profiles
- Provide User profile information given a username

### Usability requirements:
#### Primary
- Users can easily find and add Tags in an intuitive manner
- Users can update their statuses in an intuitive way that uses as few hurdles as possible
- The bot is friendly and uses calming language
- Statuses in the Ambient channel are displayed in an informative way that is easy to read
- Bot displays available commands in a list that is short and not overwhelming

#### Secondary
- User profiles are easily readable and editable

## Storyboard

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G4_1.png?raw=true" alt="storyboard of a person seeking help using the bot"/></div>

<div style="text-align:center"><img src="https://github.com/UWSocialComputing/Savanna/blob/main/_posts/img/G4_2.png?raw=true" alt="storyboard of a person providing help using the bot"/></div>

## Architecture & Data
I haven’t made a Discord bot before, but I believe all I’ll need is the bot’s code and a database. The bot would update the database as well as read from it.
Architecture: Bot <--> database
The bot’s code would probably have two main classes: the bot itself and a class for a User. 
### Bot class
#### Fields
- `List<User> ambient`		Ambient list (list of Users looking for support)
- `List<User> available` 	List of Users in “available” role
- `List<User> offering`		List of Users in “offering” role
- `List<User> do_not_disturb` List of Users in “do not disturb” role
- `const List<String> tags`	List of Tags
- `List<User> all_users`	List of all Users

#### Methods
- `create_priv_channel(User u1, User, u2)`  Creates private channel between two Users
- `structure_conv()`  Bot provides scaffolding/prompts for support
- `offer(User u, String anon_id)` Relay to the anonymous person that someone is offering to help
- `lookup(String username)` Returns the profile tags for a given User
- `all_tags()`  Returns the list of tags to choose from

### User class
#### Fields
- `String username`		Discord username
- `Bool offering`			Whether User is in offering role
- `Bool available`		Whether User is in available role
- `Bool do_not_disturb`		Whether User is in do not disturb role
- `String anon_id`		User’s anonymous id
- `List<String> profile`		List of topics User is comfortable supporting 
- `Bool looking`			Whether User is looking for support
- `Bool urgent`			Whether to send a ping
- `String support_type`		Mutual or one-sided support
- `List<String> tags`		List of Tags User wants help with
- `String message`		Message User wants sent out to get help

#### Methods
- `new_anon_id()`   Assigns new anon_id
- `update _role(String role)`   Add or remove User from the specified role
- `clear_status()`    Resets status to defaults and removes User from ambient list
- `update_profile(String updates)`    Adds/removes tags from the User’s profile
- `update_status(Bool urgent, String support_type, List<String> tags, String message)`    Updates User’s status, adds them to ambient, pings if urgent, relays their message, displays their tags

The bot’s code outline, plus an external database, as well as the scaffolding that comes built in with Discord and whatever skeleton code they have for making a bot should be enough to cover the requirements described above. In theory, the requirements above could be accomplished without a bot, and just with a server alone, however, the bot will be able to help automate and provide another layer of anonymity without requiring users to switch to a throwaway discord account or something.
