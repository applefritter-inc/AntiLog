# AntiLog
a vencord plugin to delete messages whilst bypassing vencord's messagelogger so that your message will not get logged

### current stable version: v1.2

## usage
1. right click on the message you want to delete
2. there will be an option called "AntiLog Message". click that and your message will be deleted, replaced by a block prompt that the other person's messagelogger will see, and not your original message

## how to install
```sh
git clone https://github.com/Vendicated/Vencord
cd Vencord
pnpm install --frozen-lockfile
```
now, inside the vencord directory, go to the `src/plugins` folder and make a folder named `AntiLog` \
then, move the main.tsx file inside the `AntiLog` folder \
now, run this
```sh
pnpm build
pnpm inject
```
then, use the injector that appears to inject vencord into your discord client.

## how does this work
there is a glitch on discord, where if you send one message, and if you send another message with the nonce set as the other message's id, the new message will overlap the old message, causing the old message to disappear on the client side. \
this plugin abuses that. the only issue was that the nonce trick only "hides" the message on the client's side temporarily. once you refresh, the message will reappear. therefore, a way to circumvent this is to delete both messages after sending the initial and block message. this will ensure that the message would have been removed permanently and client-side.

## settings:
`Enable Await Deletion`
there are 2 requests to delete a message in this plugin.
now, they are right beside each other, seen below

```tsx
deletemsg1()
sleep(100)
deletemsg2()
```
now, if we enable await deletion, we wait for deletemsg1 to complete first, then sleep for 100ms, before continuing to run deletemsg2.

if await deletion is disabled, we run deletemsg1, go right to the sleep 100ms delay and run deletemsg2, without waiting for deletemsg1 to complete.
this allows the script to be faster, but it is safer to use await.

`Delete Interval`
there are 2 requests to delete a message in this plugin.
now, they are right beside each other, seen below

```tsx
deletemsg1()
sleep(100)
deletemsg2()
```
now, the delete interval is the number in the sleep function.
e.g. if DeleteInterval is 120ms, sleep(120) is called.

`Block Message`
this will be the text in place of the old message that you wanted to delete. it is necessary for this plugin to work.
