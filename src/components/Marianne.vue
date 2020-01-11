<template>
    <div>
        <b-jumbotron
            header="Marianne"
            lead="Fire Emblem Three Houses Discord Bot. Displays information about character bios, combat arts, crests, DLC, focuses, personal skills, proficiencies, recruitment, and learned spells."
        >
            <b-img
                fluid
                src="https://media.discordapp.net/attachments/614902147565486111/650938572706414612/Marianne_Maid.png"
                width="300px"
                height="300px"
            ></b-img>
            <br /> <br />
            <b-button href="http://marianne-invite.hilda.pw/" size="lg" id="server" pill>Invite to your Server</b-button>&nbsp;
            <b-button href="#" id="code" size="lg" pill>View Source Code</b-button>
        </b-jumbotron>
        <b-pagination
            v-model="currentPage"
            :total-rows="totalRows"
            :per-page="perPage"
            :bg-variant="info"
            aria-controls="my-table"
            pills
            align="center"
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
    background-color: #aad0fa;
}

#server.btn.btn-secondary {
    background-color: #6174a7;
}

#code.btn.btn-secondary {
    background-color: #c8e9ff;
    color: black;
}

li.page-item {
    color: #aad0fa;
}
</style>

<script>
export default {
    data() {
        return {
        perPage: 7,
        info: "info",
        sortBy: "command_name",
        currentPage: 1,
        totalRows: 1,
        fields: [
            { key: "command_name", sortable: true },
            { key: "description", sortable: false },
            { key: "category", sortable: true },
            { key: "example", sortable: false },
            { key: "aliases", sortable: false },
            { key: "extended_help", sortable: false },
        ],
        items: [
            {
                command_name: "info",
                description: "Provides some information about this bot.",
                category: "General",
                example: "?info",
                aliases: "details, what",
                extended_help: "N/A"
            },
            {
                command_name: "invite",
                description:
                    "Displays the invite link of the bot, to invite it to your guild.",
                category: "General",
                example: "?invite",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "ping",
                description: "Runs a connection test to Discord.",
                category: "General",
                example: "?ping",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "stats",
                description: "Provides some details about the bot and stats.",
                category: "General",
                example: "?stats",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "userconf",
                description: "Define per-user settings.",
                category: "General",
                example: "?userconf",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "help",
                description: "Display help for a command.",
                category: "General",
                example: "?help",
                aliases: "commands, cmd, cmds",
                extended_help: "N/A"
            },
            {
                command_name: "uno",
                description: "References the uno meme",
                category: "Memes",
                example: "?uno",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "remindme",
                description: "Creates a reminder",
                category: "Tools",
                example: "?remindme 3hrs work on bot",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "todos",
                description: "add, remove, list user's TODOs through DM",
                category: "Tools",
                example: "?todos list",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "bio",
                description: "Replies with information about specific units",
                category: "Three Houses",
                example: "?bio Hilda",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "combatarts",
                description: "Replies with information about specific combat arts",
                category: "Three Houses",
                example: "?combatarts Sunder",
                aliases: "combat, arts",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "crest",
                description: "Replies with information about specific crests",
                category: "Three Houses",
                example: "?crest Goneril",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "dlc",
                description: "Gives details on the available DLC",
                category: "Three Houses",
                example: "?dlc",
                aliases: "N/A",
                extended_help: "N/A"
            },
            {
                command_name: "focus",
                description: "Replies with information about specific units' learning focuses",
                category: "Three Houses",
                example: "?focus Marianne",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "growths",
                description: "Replies with information about specific units' growth rates",
                category: "Three Houses",
                example: "?growths Hilda",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "personal",
                description: "Replies with information about specific units' personal skills",
                category: "Three Houses",
                example: "?growths Marianne",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "proficiencies",
                description: "Replies with information about specific units' proficiencies",
                category: "Three Houses",
                example: "?proficiencies Hilda",
                aliases: "skilllevel",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "recruit",
                description: "Replies with information about specific units' recruitments",
                category: "Three Houses",
                example: "?recruit Marianne",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
            },
            {
                command_name: "spells",
                description: "Replies with information about specific units' learned spells",
                category: "Three Houses",
                example: "?spells Hilda",
                aliases: "N/A",
                extended_help: "This command contains spoilers for Fire Emblem Three Houses!"
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