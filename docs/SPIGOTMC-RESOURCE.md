[CENTER][SIZE=7][B]CSworld[/B][/SIZE]
[SIZE=4]Cross-Server Teleportation with Free, One-Time Unlock and Per-Use Payment Modes[/SIZE][/CENTER]

[COLOR=#ff4d4d][B]Language notice:[/B][/COLOR] The SpigotMC resource page, documentation and support channel are English-only. Chinese-language support is not provided on SpigotMC.
The plugin itself currently uses Chinese for default configuration comments, player messages, administrator feedback and console messages.

[SIZE=5][B]About CSworld[/B][/SIZE]
CSworld is a lightweight cross-server teleport plugin for Paper proxy networks. Players can view configured destinations and connect by entering either the proxy server name or its configured display name. Vault integration provides three operating modes: completely free transfers, a one-time payment that permanently unlocks a destination, or a charge on every transfer.

The plugin sends the standard BungeeCord [ICODE]Connect[/ICODE] plugin message. It is intended for an existing proxy network; it does not create or manage backend servers.

[SIZE=5][B]Compatibility[/B][/SIZE]
[LIST]
[*][B]Server software:[/B] Paper 26.2 only
[*][B]Paper API used to build:[/B] 26.2.build.56-alpha
[*][B]Java:[/B] 25 or newer
[*][B]Plugin API declaration:[/B] 1.21
[*][B]Proxy requirement:[/B] A proxy network that accepts the BungeeCord [ICODE]Connect[/ICODE] plugin message
[*][B]Build validation:[/B] Maven package build completed successfully
[*][B]Testing status:[/B] No automated test sources are included and no live Paper 26.2 server test has been performed for this release
[*]Spigot server compatibility has not been tested and is not claimed
[/LIST]

[SIZE=5][B]Free Resource[/B][/SIZE]
CSworld is published as a [B]free resource[/B] at USD 0.00. The project is compact, open source under the MIT License, uses no proprietary online service and is best suited to transparent community distribution. The source code and release downloads are publicly available on GitHub.

[SIZE=5][B]Main Features[/B][/SIZE]
[LIST]
[*]Cross-server connection through the BungeeCord plugin messaging channel
[*]Destination list available with [ICODE]/cs[/ICODE]
[*]Destination lookup by proxy server key or configured display name
[*]Three-second countdown and per-player duplicate-transfer guard
[*]Manual current-server check to prevent selecting the configured local server
[*]Global free-transfer mode
[*]One-time payment mode with permanent destination unlocks
[*]Per-transfer payment mode
[*]Vault economy integration
[*]Configuration reload without a full server restart
[/LIST]

[SIZE=5][B]Transfer and Safety Behaviour[/B][/SIZE]
Only destinations explicitly listed under [ICODE]servers[/ICODE] in [ICODE]config.yml[/ICODE] can be selected. CSworld blocks a second request while the same player is already in the three-second countdown and rejects the destination configured as [ICODE]current-server[/ICODE]. The current-server value is manual; the plugin does not query the proxy to discover the actual backend server.

CSworld asks the proxy to connect the player after the countdown. It does not verify that the destination exists or is online, and it cannot confirm that the proxy completed the connection.

[SIZE=5][B]Payments and Unlock Data[/B][/SIZE]
[LIST]
[*][B]Free mode:[/B] No economy transaction is attempted.
[*][B]One-time payment:[/B] Vault withdraws the configured amount once, then the player's UUID is stored for that destination in [ICODE]plugins/CSworld/data.yml[/ICODE]. Later transfers to that destination are free.
[*][B]Per-use payment:[/B] Vault withdraws the configured amount before every connection request; no unlock record is stored.
[*]If Vault has no registered economy provider, the plugin falls back to free mode for that runtime.
[*]The unlock record is saved immediately after a successful withdrawal and before the proxy connection request.
[*]There is no automatic refund or rollback if the proxy connection fails after payment.
[/LIST]

[SIZE=5][B]Dependencies[/B][/SIZE]
[LIST]
[*][B]Vault:[/B] Required by [ICODE]plugin.yml[/ICODE]
[*][B]Economy provider:[/B] Required when using one-time or per-use payments
[*][B]Proxy network:[/B] Required for cross-server connections
[*]Paper API and Vault API are provided dependencies and are not bundled inside the release jar
[/LIST]

[SIZE=5][B]Links[/B][/SIZE]
[LIST]
[*][URL=https://github.com/yangzijian52/CSworld]Source Code[/URL]
[*][URL=https://github.com/yangzijian52/CSworld/releases]Downloads[/URL]
[*][URL=https://github.com/yangzijian52/CSworld/issues]English Support and Issues[/URL]
[*][URL=https://github.com/yangzijian52/CSworld/blob/main/LICENSE]MIT License[/URL]
[/LIST]

[SIZE=5][B]Important Notes[/B][/SIZE]
[LIST]
[*]CSworld is designed for Paper 26.2 proxy networks, not standalone single-server teleportation.
[*]Vault is declared as a required plugin and must be installed even when [ICODE]free-mode[/ICODE] is enabled.
[*]Paid modes require a Vault-compatible economy provider.
[*]Use non-negative whole numbers for destination costs.
[*]Destination display names should not contain spaces because the command reads one destination argument.
[*]Back up [ICODE]plugins/CSworld/data.yml[/ICODE] before replacing or editing unlock data.
[*]No automatic refund is available when a proxy transfer fails after a successful charge.
[*]The plugin interface is currently Chinese, while the SpigotMC page, documentation and support are English-only.
[/LIST]
