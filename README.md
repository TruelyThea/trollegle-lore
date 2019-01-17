# Trollegle Lore #

---

## What is Trollegle? ##

*Trollegle* is a java application that enables group chat on [Omegle.com](https://www.omegle.com/). It is a *bot* that relays users' messages to the rest of the room.

## Trollegle how-to ##

### Joining the chat ###

Chat rooms send out *pulses*, or searches for new users. Pulses search for users with specific interest topics on the text-mode chat. These interests are specific to the pulse; hence, they are volatile and change often. Someone who wants to join the chat needs to add the appropriate topics. Every actively pulsing chat room is listed along with it's pulse topics at [Bellawhiskey](https://bellawhiskey.ca/trollegle/). Every user visits Bellawhiskey (often shortened to bw) before accessing the chat.

### Using the chat ###

You can send a message like you would on a regular Omegle chat. However, a Trollegle chat can do more. It features a number of *commands* to do specific actions. Typing `/help` for example should list the available commands. Typing `/rules` should tell you how users are expected to behave. At the very beginning of a message the character `/` indicates that the next word is a command. The available commands are a variant of the popular [Internet Relay Chat (IRC)](https://en.wikipedia.org/wiki/Internet_Relay_Chat) interface, but the set of available commands isn't identical to this interface.

Some commands take *arguments*, or values that the command uses while performing it's action. The `/help` documentation will usually list these in capital letters in the order they should appear. One example is `/nick NAME`. The `/nick` command changes your nickname, which is displayed in front of every message you send. `NAME` is an argument, and is therefore a place holder for an arbitrary word. If you type `/nick Doug`, then you'll nickname will become `Doug`. If you then type a message, like `hello everyone!`, everyone will see the message `[Doug] hello everyone!`.

The `/me` command is used to tell everyone about an action you're doing. It takes an arbitrary list of arguments, which are simply treated as the words in a sentence. If you type `/me is very hungry.`,
then a message will be sent to the room that says: `* [YourNickname] is very hungry.`

Often commands take a user as an argument, here you may type either the user's nickname or the user's *id*, which is a unique integer identifying the user. The command `/showids` will show a user's id in front of the their name in their messages. The command `/hideids` will undo this. Also the command `/list` will show you the list of users along with their ids. A user's id lasts for their entire session, that is until they leave. It's possible that another user will acquire their id if they join after the user leaves.

One command that takes a user is `/pat USER`. This will show announcement to the room saying that you patted the user. Pats are usually meant as a friendly gesture or a way of saying thank you. If you type `/pat Winifred`, then everyone will see the announcement `| [YourNickname] pats Winifred (pat count: 5)`. If Winifred's id is `8`, then you could also type `/pat 8`. The pat count increments with every pat a user gets.

If you type an invalid argument, like a user that doesn't exist, or you don't give the proper number of arguments, you should see an error message describing what went wrong.

Many commands have *aliases* or other names that you can use instead of the commands. A lot of these are much shorter, for example `/n` can be used instead of `/nick` and `/dids` instead of `/showids`. Unfortunately these aliases are not listed under `/help`, and you will need to look at the code in `UserBehavior.java` to find the aliases. All of the java source code for Trollegle is available [here](https://gitlab.com/jtrygva/trollegle). This means that any user can host their own chat room.

The user that is hosting the chat room is referred to as the *admin*. They have a special, fixed id, `0`. The admin has access to plenty of special admin commands. Many admins host a modified version of the chat room that provides additional admin and user commands. Sometimes the standard behaviors described above won't apply in a modified chat room, depending on how it was built.

If a user hasn't sent a message for a while, they are marked as a *lurker*. Other users cannot see lurkers or what they say, but lurkers can see other lurkers and what they say. Lurkers don't appear in regular users' `/list`, but they do appear in other lurkers' `/list`. `/nolurk` prevents a user from ever lurking and unlurks a lurking user, and `/lurk` reenables lurking.

If a user has been inactive for a while (hasn't sent any message or command), then they are kicked from the chat. There is no command to prevent this; however, the [userscript](https://bellawhiskey.ca/trollegle/trollegle.js) includes an option to send a command periodically to prevent inactivity.

## About these pages ##

This repository aims to be a documentation of Trollegle / an encyclopedia. There is a [Fandom](http://trollegle2.wikia.com/wiki/Trollegle_Wiki) site for Trollegle, too, but it is quite incomplete. Feel free to make a pull request to this repository.

TODO: A page about the admin commands and hosting a chat, a page about the userscript, pages about Trollegle lore.
