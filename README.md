# -> Informations <-
This is just a code snippet that is developed for the [discord4py](https://github.com/mccoderpy/discord.py-message-components) **python** library.

<br>
<br>

# Usage

## Specials
| `Name`                     | Description                                   | Prefixes       |
| :---                       |    :----:                                     |           ---: |
| Basic bot                  | Create a basic bot                            | `%bot`        |
| Advanced bot               | Create an advanced bot                        | `%bot_advanced`|
| Help command               | The help command for the bot in main file     | `%help`        |
| Cog                        | Create a cog                                  | `%cog`         |
| Command cooldown           | Set the cooldown of a command                 | `%cooldown`    |
| Member has role to command | Check if the caller has the specified role    | `%cmdhasrole`  |
| Command Error decorator    | Create a custom response to a command error   | `errorcmd`     |
| Get                        | Iterate a list of data with discord.utils.get | `%get`         |
| Wait for                   | Wait for the event of a certain member        | `%wait`        |

<br>

## Components
| `Name`                     | Description                                 | Prefixes      |
| :---                       |    :----:                                   |          ---: |
| Button                     | Create a button                             | `%button`     |
| SelectMenu                 | Create a SelectMenu                         | `%selectmenu`  |
| Modal                      | Create a Modal                              | `%modal`      |     

<br>

## Outside of a cog
| `Name`                       | Description                      | Prefixes             |
| :---                         |    :----:                        |                 ---: |
| Command                      | A complete command               | `%cmd`               |
| Basic command                | Just a basic command             | `%cmdb`              |
| Slash command                | Application/Slash command        | `%slash`             |
| Check                        | Create a check                   | `%check`             |
| Base event                   | Event base                       | `%event`             |
| Member evets                 | Containing various member events | `%event_member`      |
| Guild events                 | Containing various guild events  | `%event_guild`       |
| Message events               | Containing various events        | `%event_message`     |
| Event button is pressed      | Event when a button is pressed   | `%button_click`      |
| Event selectmenu is selected | Event when select an option      | `%selectmenu_select` |
| Event modal is sended        | Event when a bot modal is sent   | `%modal_send`        |

<br>

## Inside a cog
| `Name`                       | Description                      | Prefixes               |
| :---                         |    :----:                        |                   ---: |
| Command                      | A complete command               | `%cgcmd`               |
| Basic command                | Just a basic command             | `%cgcmdb`              |
| Slash command                | Application/Slash command        | `%cgslash`             |
| Check                        | Create a check                   | `%cgcheck`             |
| Base event                   | Event base                       | `%cgevent`             |
| Member evets                 | Containing various member events | `%cgevent_member`      |
| Guild events                 | Containing various guild events  | `%cgevent_guild`       |
| Message events               | Containing various events        | `%cgevent_message`     |
| Event button is pressed      | Event when a button is pressed   | `%cgbutton_click`      |
| Event selectmenu is selected | Event when select an option      | `%cgselectmenu_select` |
| Event modal is sended        | Event when a bot modal is sent   | `%cgmodal_send`        |

<br>

## Embed
| `Name`                    | Description                      | Prefixes        |
| :---                      |    :----:                        |          ---:   |
| Embed base                | Create a embed                   | `%emb`          |
| Embed author              | Put the author in the embed      | `%embauthor`    |
| Embed Field               | Add a field to an embed          | `%embfield`     |
| Embed image               | Set an image for an embed        | `%embimg`       |
| Embed thumbail            | Set a thumbnail for an embed     | `%embthum`      |
| Embed footer              | Put a footer for an embed        | `%embfoot`       |




## Examples
```py
#Check
async def is_owner(ctx):
    if ctx.author.id == bot.owner_id:
        return True
    else:
        return False

@bot.command()
@commands.check(is_owner)
async def pong(ctx):
    #Wait for
    try:
        message = bot.wait_for("message", check= lambda interaction: interaction.author.id == ctx.author.id and interaction.channel.id == ctx.channel.id, timeout=30)
    except asyncio.TimeoutError:
        return await ctx.send("You took too long to reply")

    #Get
    role = discord.utils.get(id=1059889859682426234, ctx.author.roles)

```