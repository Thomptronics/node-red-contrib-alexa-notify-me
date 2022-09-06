# node-red-contrib-alexa-notify-me
A Node-RED node to send Alexa Notifications via the [Notify Me skill by Thomptronics](https://amzn.to/3qenUdA). To learn more about Notify Me, please visit www.notifymyecho.com


IMPORTANT NOTE: Notify Me is only available in the countries that allow English-speaking Alexa skills.

## Install
Run the following npm command in your Node-RED user directory (typically ~/.node-red):
```
npm install @thomptronics/node-red-contrib-alexa-notify-me
```

## Node Configuration

### Access Code
Put your ```Access Code``` in the node's Properties tab.  The ```Access Code``` is required for communications with Alexa.

See www.notifymyecho.com for detailed information how to get your own unique access code.


### Notification
The ```Notification```  string you want to send can be put in the node's Properties tab or passed in via ```msg.payload```. A notification found in the node's Properties tab will override one passed in <code>msg.payload</code>, so be sure to empty the Properties' Notification field if you want to pass your notification via the payload.

You must specify a notification string in either the Properties tab or in ```msg.payload``` since there would be no point in sending an empty notification.


### Title
The ```Title``` string appears on Echo Show screens when the notification arrives. A title passed in <code>msg.topic</code> will override any title found in the node's Properties tab.</p> A title is optional and, if not specified by either ```msg.topic``` or the Properties tab, defaults to "Notification from Yourself."

## Node Usage
The following flow is a simple example of how to use this node:
```
[{"id":"66f244c7099a0e6d","type":"tab","label":"Alexa Notify Me","disabled":false,"info":"","env":[]},{"id":"d6a18213066005c6","type":"notify-me","z":"66f244c7099a0e6d","name":"","title":"Greetings from Node-RED","notification":"","x":300,"y":160,"wires":[["6b53158ace42fb38"]]},{"id":"df7c875d569b70e7","type":"inject","z":"66f244c7099a0e6d","name":"","props":[{"p":"payload"}],"repeat":"","crontab":"","once":false,"onceDelay":0.1,"topic":"","payload":"Hello World","payloadType":"str","x":130,"y":160,"wires":[["d6a18213066005c6"]]},{"id":"6b53158ace42fb38","type":"debug","z":"66f244c7099a0e6d","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"true","targetType":"full","statusVal":"","statusType":"auto","x":450,"y":160,"wires":[]},{"id":"4e8a327792b14c89","type":"comment","z":"66f244c7099a0e6d","name":"Press the 'Hello World' inject button below to send a notification to your Alexa devices...","info":"","x":340,"y":100,"wires":[]},{"id":"a0bc665065b873b1","type":"comment","z":"66f244c7099a0e6d","name":"Prerequisites (double click on this to view)","info":" Before you can use this node, you must:\n - Enable the Notify Me skill by Thomptronics\n - Launch the skill to trigger your access code email\n - Enter your Access Code in the node's Properties tab\n \nPlease visit www.notifymyecho.com for details\n ","x":200,"y":40,"wires":[]}]
```
