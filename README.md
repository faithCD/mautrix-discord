# mautrix-discord (Modified Fork)
This is a modified fork of [mautrix-discord](https://github.com/mautrix/discord) based on [discordgo](https://github.com/bwmarrin/discordgo).

## Changes in This Fork

This fork disables **direct media for avatars only** even if the config.yaml has direct_media enabled.
Additionally, it implements a hacky-workaround for custom emotes to be bridged and recognized to guilds accordingly [(see here for more info)](https://github.com/faithCD/mautrix-discord-emoji-pipe).

### Reason

Some Synapse homeserver configurations reject remote `mxc://` avatar media
if it is not already present in the local media repository cache. Disabling
direct media for avatars only ensures that mautrix-discord defaults to 
copying the attachment to the main matrix homeserver.

No other direct media functionality has been modified.

## Documentation
All setup and usage instructions are located on [docs.mau.fi]. Some quick links:

[docs.mau.fi]: https://docs.mau.fi/bridges/go/discord/index.html

* [Bridge setup](https://docs.mau.fi/bridges/go/setup.html?bridge=discord)
  (or [with Docker](https://docs.mau.fi/bridges/general/docker-setup.html?bridge=discord))
* Basic usage: [Authentication](https://docs.mau.fi/bridges/go/discord/authentication.html),
  [Relaying with webhooks](https://docs.mau.fi/bridges/go/discord/relay.html)

### Features & Roadmap
[ROADMAP.md](https://github.com/mautrix/discord/blob/main/ROADMAP.md)
contains a general overview of what is supported by the bridge.

## Discussion
Upstream Matrix room: [#discord:maunium.net](https://matrix.to/#/#discord:maunium.net)

## License

This project remains licensed under the GNU Affero General Public License v3.0 (AGPLv3),
in accordance with the original project.

#### NOTE:
This patch is intentionally minimal and very crude. As this is not my primary programming
language, I opted for a small modification rather than introducing new
configuration or HTML parsing structures.
