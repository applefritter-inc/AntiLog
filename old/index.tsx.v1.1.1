import { definePluginSettings } from "@api/Settings";
import { addButton, removeButton } from "@api/MessagePopover";
import definePlugin, { OptionType } from "@utils/types";
import { ChannelStore, Constants, RestAPI, UserStore } from "@webpack/common";
import { findByPropsLazy } from "@webpack";
const MessageActions = findByPropsLazy("deleteMessage", "startEditMessage");

const settings = definePluginSettings({
    deleteInterval: {
        type: OptionType.NUMBER,
        description: "delay between old and block message deletion. set to 50ms by default. this is to prevent API spam if deleting goes too fast. setting this value too high will cause a high delay, and might cause the plugin to not work properly when deleting.",
        default: 50
    },
    blockMessage: {
        type: OptionType.STRING,
        description: "string to display to people who try to log the message.",
        default: "message logging blocked with an anti-messagelogger plugin."
    },
});

const AntiLogIcon = () => {
    return <svg version="1.1" x="0px" y="0px" viewBox="0 0 256 256" width="18" height="18" fill="currentColor">
        <g><g><g>
            <path d="M77.1,25c-46.1,13.8-49.8,15-51,16.3l-1.3,1.4l0.1,58.4l0.1,58.4l1.3,4.6c5.9,21.1,26.3,43,57.7,61.9c12.2,7.3,27.2,14.4,38.3,18.2l5.6,1.9l3.4-1.1c6.7-2.2,15.5-5.8,24.8-10.5c20.4-10.1,36.5-21.2,49.9-34.3c14.2-13.8,22.1-26.9,24.5-40.5c0.6-3.3,0.7-12.6,0.7-60.4V42.7l-1.2-1.4c-1.2-1.3-5.2-2.5-51.2-16.4c-27.5-8.2-50.4-15-50.9-14.9C127.3,10,104.5,16.7,77.1,25z M133.8,50.5c2.3,1,5.3,3.6,6.7,5.8c1.7,2.8,2.5,2.9,17.5,2.9c13.1,0,13.5,0,16.9,1.2c5.8,2,9.8,5,13.2,10.1c3.2,4.8,3.8,7.9,3.8,17.7c0,8.2,0,8.6-1.2,11.1c-1.6,3.3-3.9,5.7-7.3,7.4c-1.5,0.8-3,1.8-3.4,2.4c-0.4,0.6-3.5,16-7,34.3c-4.2,22.3-6.5,33.9-7.2,35.1c-1.4,2.9-4,5.3-6.8,6.7l-2.6,1.3H128H99.7l-2.6-1.3c-2.9-1.4-5.3-3.9-6.8-6.7c-0.6-1.3-2.9-12.5-7.2-35.1c-3.4-18.3-6.5-33.8-6.9-34.3c-0.4-0.6-1.9-1.7-3.4-2.4c-3.4-1.7-5.8-4.1-7.3-7.4c-1.2-2.4-1.2-2.8-1.2-11.1c0-7.5,0.1-8.9,1-11.7c2.5-8,8.8-14,17.1-16.5c2.1-0.6,4.9-0.7,15.8-0.7c14.8,0,15.7-0.1,17.4-2.9c1.2-1.9,4.1-4.6,6-5.6C124.9,49,130.2,48.9,133.8,50.5z" />
            <path d="M124.7,60.6c-1.4,1.2-1.5,1.6-1.7,4.8l-0.2,3.5l-19,0.1L85,69.1l-2.6,1.3c-2.9,1.4-5.3,3.8-6.9,6.9c-0.9,1.8-1.1,2.7-1.2,9.5c-0.2,8.3,0.1,9.9,2.3,10.9c0.8,0.4,2.6,0.7,4.8,0.7c1.9,0,3.5,0.1,3.5,0.2c0,1.6,14,74.6,14.5,75.7c1.3,2.9,1.2,2.9,28.8,2.9c27.6,0,27.5,0,28.8-2.9c0.5-1.1,14.5-74.1,14.5-75.7c0-0.1,1.6-0.2,3.5-0.2c2.2,0,4-0.3,4.8-0.7c2.1-1.1,2.4-2.6,2.3-10.9c-0.1-6.8-0.3-7.7-1.2-9.5c-1.6-3-4.1-5.5-6.9-6.9l-2.6-1.3L152.2,69l-19-0.1l-0.2-3.5c-0.1-3.3-0.3-3.6-1.7-4.8c-1.1-1-1.9-1.3-3.3-1.3C126.6,59.2,125.8,59.6,124.7,60.6z M115.3,108.7c0.8,0.4,1.7,1.2,2.1,1.7c0.6,1,5.6,38.1,5.6,41.7c0,4.5-4.7,6.8-7.9,3.9l-1.5-1.3l-2.7-21.1c-2.5-19.7-2.6-21.1-1.9-22.6c0.6-1.4,2.9-2.9,4.2-2.9C113.6,108.1,114.5,108.4,115.3,108.7z M144.8,108.8c0.9,0.4,1.8,1.4,2.3,2.2c0.6,1.4,0.6,2.8-1.8,21.7c-1.4,11.1-2.6,20.6-2.8,21.1c-0.5,1.5-2.1,2.9-3.7,3.3c-3.1,0.6-5.7-1.6-5.7-5c0-3.6,5-40.8,5.6-41.7c0.6-1,2.9-2.3,4-2.4C143,108.1,144,108.4,144.8,108.8z" />
        </g></g></g>
    </svg>;
};

function messageSendWrapper(content, nonce, channelId) {
    const wrapperResponse = RestAPI.post({
        url: Constants.Endpoints.MESSAGES(channelId),
        body: {
            content: content,
            flags: 0,
            mobile_network_type: "unknown",
            nonce: nonce,
            tts: false,
        }
    });
    return wrapperResponse;
}

async function sleep(ms: number): Promise<void> {
    return new Promise((resolve) => setTimeout(resolve, ms));
}

function deleteWrapper(channelId, messageId) {
    MessageActions.deleteMessage(channelId, messageId);
}

export default definePlugin({
    name: "AntiLog",
    description: "abuses a discord client side glitch to mask your deleted message, so a user with vencord's messagelogger plugin enabled will not be able to see the deleted message.",
    authors: [{ name: "appleflyer", id: 1209096766075703368n }],
    dependencies: ["MessagePopoverAPI"],
    settings,
    start() {
        addButton("AntiLog", msg => {
            // sanity checks for people who randomly do shit
            const isMessageOwner = msg.author.id === UserStore.getCurrentUser().id;
            const channel_id = msg.channel_id;
            if (!isMessageOwner) return null;

            // async so promise can resolve
            const handleClick = async () => {
                // send the bugged message
                const toDeleteId = msg.id;
                const buggedMsgResponse = await messageSendWrapper(settings.store.blockMessage, msg.id, msg.channel_id);
                const buggedMsgId = buggedMsgResponse.body.id;
                // delete initial and block message messages
                await deleteWrapper(channel_id, toDeleteId);
                sleep(settings.store.deleteInterval);
                await deleteWrapper(channel_id, buggedMsgId);
            };
            return {
                label: "AntiLog Message",
                icon: AntiLogIcon,
                message: msg,
                channel: ChannelStore.getChannel(msg.channel_id),
                onClick: handleClick
            };
        });
    },

    stop() {
        removeButton("AntiLog");
    }
});
