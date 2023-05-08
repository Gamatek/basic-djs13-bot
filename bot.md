# Creation of your bot with DiscordJS v13

<img src="./assets/discordjs.svg">

Package required: `npm i discord.js@13`

With the arrival of DiscordJS v13, we must now give the *intents* of our bot. The `GUILDS` intent is required.

```js
const { Client, Intents } = require("discord.js")

const client = new Client({
intents: [
Intents.FLAGS.GUILDS
]
})

client.on("ready", () => {
console.log(`Logged in as ${client.user.ta}`)
})

client.login("TOKEN_BOT")
```

### List of intents
```
GUILDS
GUILD_MEMBERS *
GUILD_BANS
GUILD_EMOJIS_AND_STICKERS
GUILD_INTEGRATIONS
GUILD_WEBHOOKS
GUILD_INVITES
GUILD_VOICE_STATES
GUILD_PRESENCES *
GUILD_MESSAGES
GUILD_MESSAGE_REACTIONS
GUILD_MESSAGE_TYPING
GUILD_SCHEDULED_EVENTS

DIRECT_MESSAGES
DIRECT_MESSAGE_REACTIONS
DIRECT_MESSAGE_TYPING

MESSAGE_CONTENT *

AUTO_MODERATION_CONFIGURATION
AUTO_MODERATION_EXECUTION

* Privileged Gateway Intents
```

### List of events
```
warn: [message: string]
ready: [client: Client<true>]
cacheSweep: [message: string]
interactionCreate: [interaction: Interaction]
applicationCommandPermissionsUpdate: [data: ApplicationCommandPermissionsUpdateData]
presenceUpdate: [oldPresence: Presence | null, newPresence: Presence]
invalidated: []
error: [error: Error]
typingStart: [typing: Typing]
userUpdate: [oldUser: User | PartialUser, newUser: User]
voiceStateUpdate: [oldState: VoiceState, newState: VoiceState]
webhookUpdate: [channel: TextChannel | NewsChannel | VoiceChannel | ForumChannel]

shardDisconnect: [closeEvent: CloseEvent, shardId: number]
shardError: [error: Error, shardId: number]
shardReady: [shardId: number, unavailableGuilds: Set<Snowflake> | undefined]
shardReconnecting: [shardId: number]
shardResume: [shardId: number, replayedEvents: number]

guildScheduledEventCreate: [guildScheduledEvent: GuildScheduledEvent]
guildScheduledEventUpdate: [oldGuildScheduledEvent: GuildScheduledEvent, newGuildScheduledEvent: GuildScheduledEvent]
guildScheduledEventDelete: [guildScheduledEvent: GuildScheduledEvent]
guildScheduledEventUserAdd: [guildScheduledEvent: GuildScheduledEvent, user: User]
guildScheduledEventUserRemove: [guildScheduledEvent: GuildScheduledEvent, user: User]
guildAuditLogEntryCreate: [auditLogEntry: GuildAuditLogsEntry, guild: Guild]
guildBanAdd: [ban: GuildBan]
guildBanRemove: [ban: GuildBan]
guildCreate: [guild: Guild]
guildDelete: [guild: Guild]
guildUnavailable: [guild: Guild]
guildIntegrationsUpdate: [guild: Guild]
guildMemberAdd: [member: GuildMember]
guildMemberAvailable: [member: GuildMember | PartialGuildMember]
guildMemberRemove: [member: GuildMember | PartialGuildMember]
guildMembersChunk: [
    lmembers: Collection<Snowflake, GuildMember>,
    lguild: Guild,
    ldata: { count: number index: number nonce: string | undefined notFound: unknown[] },
]
guildMemberUpdate: [oldMember: GuildMember | PartialGuildMember, newMember: GuildMember]
guildUpdate: [oldGuild: Guild, newGuild: Guild]

autoModerationActionExecution: [autoModerationActionExecution: AutoModerationActionExecution]
autoModerationRuleCreate: [autoModerationRule: AutoModerationRule]
autoModerationRuleDelete: [autoModerationRule: AutoModerationRule]
autoModerationRuleUpdate: [
    loldAutoModerationRule: AutoModerationRule | null,
    lnewAutoModerationRule: AutoModerationRule,
]

channelCreate: [channel: NonThreadGuildBasedChannel]
channelDelete: [channel: DMChannel | NonThreadGuildBasedChannel]
channelPinsUpdate: [channel: TextBasedChannel, date: Date]
channelUpdate: [
    loldChannel: DMChannel | NonThreadGuildBasedChannel,
    lnewChannel: DMChannel | NonThreadGuildBasedChannel,
]

messageCreate: [message: Message]
messageDelete: [message: Message | PartialMessage]
messageReactionRemoveAll: [
    lmessage: Message | PartialMessage,
    lreactions: Collection<string | Snowflake, MessageReaction>,
]
messageReactionRemoveEmoji: [reaction: MessageReaction | PartialMessageReaction]
messageDeleteBulk: [messages: Collection<Snowflake, Message | PartialMessage>]
messageReactionAdd: [reaction: MessageReaction | PartialMessageReaction, user: User | PartialUser]
messageReactionRemove: [reaction: MessageReaction | PartialMessageReaction, user: User | PartialUser]
messageUpdate: [oldMessage: Message | PartialMessage, newMessage: Message | PartialMessage]

emojiCreate: [emoji: GuildEmoji]
emojiDelete: [emoji: GuildEmoji]
emojiUpdate: [oldEmoji: GuildEmoji, newEmoji: GuildEmoji]

stickerCreate: [sticker: Sticker]
stickerDelete: [sticker: Sticker]
stickerUpdate: [oldSticker: Sticker, newSticker: Sticker]

inviteCreate: [invite: Invite]
inviteDelete: [invite: Invite]

roleCreate: [role: Role]
roleDelete: [role: Role]
roleUpdate: [oldRole: Role, newRole: Role]

threadCreate: [thread: ThreadChannel, newlyCreated: boolean]
threadDelete: [thread: ThreadChannel]
threadListSync: [threads: Collection<Snowflake, ThreadChannel>]
threadMemberUpdate: [oldMember: ThreadMember, newMember: ThreadMember]
threadMembersUpdate: [
    loldMembers: Collection<Snowflake, ThreadMember>,
    lnewMembers: Collection<Snowflake, ThreadMember>,
]
threadUpdate: [oldThread: ThreadChannel, newThread: ThreadChannel]

stageInstanceCreate: [stageInstance: StageInstance]
stageInstanceUpdate: [oldStageInstance: StageInstance | null, newStageInstance: StageInstance]
stageInstanceDelete: [stageInstance: StageInstance]
```