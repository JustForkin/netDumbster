[![Build status](https://ci.appveyor.com/api/projects/status/su9xd1ddo1bv5q4i?svg=true)](https://ci.appveyor.com/project/cmendible/netdumbster)

[![Build Status](https://dev.azure.com/mendible/mendible/_apis/build/status/netDumbster)](https://dev.azure.com/mendible/mendible/_build/latest?definitionId=1)

# netDumbster 
is a .Net Fake SMTP Server clone of the popular Dumbster (http://quintanasoft.com/dumbster/)

netDumbster is based on the API of nDumbster (http://ndumbster.sourceforge.net/default.html) and the nice C# Email Server (CSES) written by Eric Daugherty.

License: http://www.apache.org/licenses/LICENSE-2.0.html

# Usage

Create a netDumbster Server instance:
````
var server = SimpleSmtpServer.Start(port);
````

Check received email count:
````
var count = server.ReceivedEmailCount
````

Get the body of the first email received:
````
var smtpMessage = server.ReceivedEmail[0];
var body = smtpMessage.MessageParts[0].BodyData
```` 

Subscribe to the message received event:
````
server.MessageReceived += (sender, args) =>
    {
        // Get message body.
        var body = args.Message.MessageParts[0].BodyData;
    };
````