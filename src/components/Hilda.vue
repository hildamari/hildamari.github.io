<template>
    <div>
        <b-jumbotron
            header="Hilda"
            lead="Fire Emblem Three Houses Discord Bot brought to you by memes for memes."
            bg-variant="pink"
        >
            <b-img
                fluid
                src="https://cdn.discordapp.com/attachments/614902147565486111/643891293839163434/Hilda_Maid.png"
                width="300px"
                height="300px"
            ></b-img>
            <br /> <br />
            <b-button href="http://hilda-invite.hilda.pw/" id="server" size="lg" pill>Invite to your Server</b-button>&nbsp;
            <b-button href="https://github.com/hildamari/Hilda" id="code" size="lg" pill>View Source Code</b-button>
        </b-jumbotron>
        <b-pagination
            v-model="currentPage"
            :total-rows="totalRows"
            :per-page="perPage"
            :bg-variant="primary"
            aria-controls="my-table"
            pills
            align="center"
            class="bg-pink"
            size="lg"
        ></b-pagination>
        <hr />
        <b-table
            id="my-table"
            :items="items"
            :fields="fields"
            :sort-by.sync="sortBy"
            :per-page="perPage"
            :current-page="currentPage"
            small
        ></b-table>
    </div>
</template>

<style scoped>
.jumbotron {
    background-color: #fcafb7;
}

#server.btn.btn-secondary {
    background-color: #aa575f;
}

#code.btn.btn-secondary {
    background-color: #feb9b3;
    color: black;
}

li.page-item {
    color: #fcafb7;
}
</style>

<script>
export default {
    data() {
        return {
            perPage: 8,
            primary: "primary",
            sortBy: "command_name",
            currentPage: 1,
            totalRows: 1,
            fields: [
                { key: "command_name", sortable: true },
                { key: "description", sortable: false },
                { key: "category", sortable: true },
                { key: "example", sortable: false },
                { key: "aliases", sortable: false },
                { key: "extended_help", sortable: false }
            ],
            items: [
                {
                    command_name: "info",
                    description: "Provides some information about this bot.",
                    category: "General",
                    example: "!info",
                    aliases: "details, what",
                    extended_help: "N/A"
                },
                {
                    command_name: "invite",
                    description:
                        "Displays the invite link of the bot, to invite it to your guild.",
                    category: "General",
                    example: "!invite",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "ping",
                    description: "Runs a connection test to Discord.",
                    category: "General",
                    example: "!ping",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "stats",
                    description: "Provides some details about the bot and stats.",
                    category: "General",
                    example: "!stats",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "userconf",
                    description: "Define per-user settings.",
                    category: "General",
                    example: "!userconf",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "help",
                    description: "Display help for a command.",
                    category: "General",
                    example: "!help",
                    aliases: "commands, cmd, cmds",
                    extended_help: "N/A"
                },
                {
                    command_name: "fc",
                    description: "Gives your friend code or another user's friend code",
                    category: "Friend Code",
                    example: "!fc",
                    aliases: "details, what",
                    extended_help: "N/A"
                },
                {
                    command_name: "setfc",
                    description: "Sets your friend code",
                    category: "Friend Code",
                    example: "!setfc SW-8329-0107-7411",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "coinflip",
                    description: "Flip a coin",
                    category: "Fun",
                    example: "!coinflip",
                    aliases: "coin",
                    extended_help: "N/A"
                },
                {
                    command_name: "dice",
                    description: "Roll a 6-sided die",
                    category: "Fun",
                    example: "!dice",
                    aliases: "die, roll",
                    extended_help: "N/A"
                },
                {
                    command_name: "8ball",
                    description: "Ask the eightball a question, get a random response.",
                    category: "Fun",
                    example: "!8ball",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "fortune",
                    description: "Replies with a random fortune",
                    category: "Fun",
                    example: "!fortune",
                    aliases: "cookie",
                    extended_help: "N/A"
                },
                {
                    command_name: "quote",
                    description: "Quote a message using a message ID",
                    category: "Fun",
                    example: "!quote",
                    aliases: "add, pin",
                    extended_help: "N/A"
                },
                {
                    command_name: "about",
                    description: "Replies with information about the bot",
                    category: "Info",
                    example: "!info",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "emoji",
                    description: "Displays the server's emoji",
                    category: "Info",
                    example: "!emoji",
                    aliases: "listemoji",
                    extended_help: "N/A"
                },
                {
                    command_name: "ahselk",
                    description: "Sends with AhSelk image",
                    category: "Memes",
                    example: "!ahselk",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "ahshit",
                    description: "Sends with AhShit image",
                    category: "Memes",
                    example: "!ahshit",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "hilda",
                    description: "Chants HIL-DA HIL-DA and plays the voice clip",
                    category: "Memes",
                    example: "!hilda",
                    aliases: "chant",
                    extended_help: "N/A"
                },
                {
                    command_name: "eirika",
                    description: "Sends with HDNotLikeEirika image",
                    category: "Memes",
                    example: "!eirika",
                    aliases: "hdnotlikeeirika, hd",
                    extended_help: "N/A"
                },
                {
                    command_name: "flayn",
                    description: "Sends a very short parody of Edge of Dawn, Flayn style",
                    category: "Memes",
                    example: "!flayn",
                    aliases: "fishy",
                    extended_help: "N/A"
                },
                {
                    command_name: "imbaby",
                    description: "Sends the im baby image",
                    category: "Memes",
                    example: "!imbaby",
                    aliases: "baby",
                    extended_help: "N/A"
                },
                {
                    command_name: "nolewds",
                    description: "Replies with the nolewds image",
                    category: "Memes",
                    example: "!nolewds",
                    aliases: "lewds, lewd",
                    extended_help: "N/A"
                },
                {
                    command_name: "readme",
                    description: "Sends Moonling's readme image",
                    category: "Memes",
                    example: "!readme",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "uno",
                    description: "References the uno meme",
                    category: "Memes",
                    example: "!uno",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "reply",
                    description: "Replies with a message",
                    category: "Memes",
                    example: "!reply",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "iswhy",
                    description: "Replies with the IS why gif",
                    category: "Memes",
                    example: "!iswhy",
                    aliases: "why",
                    extended_help: "N/A"
                },
                {
                    command_name: "work",
                    description: "Replies with 'You're making me work!'",
                    category: "Memes",
                    example: "!work",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "level",
                    description: "Check your current level",
                    category: "Social",
                    example: "!level",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "points",
                    description: "Check how many points you have",
                    category: "Social",
                    example: "!points",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "hoesmad",
                    description: "Sends the HoesMad image",
                    category: "Memes",
                    example: "!hoesmad",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "joesmad",
                    description: "Sends the JoesMad image",
                    category: "Memes",
                    example: "!joesmad",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "doesmad",
                    description: "Sends the DoesMad image",
                    category: "Memes",
                    example: "!doesmad",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "sweaty",
                    description: "Replies with 'I'm all sweaty!'",
                    category: "Memes",
                    example: "!sweaty",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "ferdinand",
                    description: "Plays the 'I am Ferdinand von Aegir' voice clip",
                    category: "Memes",
                    example: "!ferdinand",
                    aliases: "N/A",
                    extended_help: "N/A"
                },
                {
                    command_name: "leave",
                    description: "Makes the bot leave voice channel if it is in one",
                    category: "Music",
                    example: "!leave",
                    aliases: "end",
                    extended_help: "N/A"
                },
                {
                    command_name: "nowplaying",
                    description: "Shows the current status of the music.",
                    category: "Music",
                    example: "!nowplaying",
                    aliases: "np",
                    extended_help: "N/A"
                },
                {
                    command_name: "pause",
                    description: "Pause the current playing song",
                    category: "Music",
                    example: "!pause",
                    aliases: "hold, stop",
                    extended_help: "N/A"
                },
                {
                    command_name: "play",
                    description: "Play any song from YouTube",
                    category: "Music",
                    example: "!play https://www.youtube.com/watch?v=oNFGZ30KXKM",
                    aliases: "add",
                    extended_help: "Use the command again to remove the role"
                },
                {
                    command_name: "resume",
                    description: "Resume the current paused song",
                    category: "Music",
                    example: "!resume",
                    aliases: "continue",
                    extended_help: "N/A"
                },
                {
                    command_name: "skip",
                    description: "Skip the current playing song",
                    category: "Music",
                    example: "!skip",
                    aliases: "skip-song, advance-song, advance",
                    extended_help: "N/A"
                },
                {
                    command_name: "queue",
                    description: "Display the song queue",
                    category: "Music",
                    example: "!next",
                    aliases: "song-list, next-songs, q",
                    extended_help: "N/A"
                },
                {
                    command_name: "subscribe",
                    description: "Gives the 'Hilda Subscriber' role to those who want to be notified of new updates",
                    category: "Support Server",
                    example: "!subscribe",
                    aliases: "N/A",
                    extended_help: "Use the command again to remove the role. This command can only be used in the support server."
                }
            ]
        };
    },
    mounted() {
      // Set the initial number of items
      this.totalRows = this.items.length
    }
}
</script>
