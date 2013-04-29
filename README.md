Pushover4j
--------

A java client for [pushover](https://pushover.net/)

```
PushoverClient client = new PushoverRestClient();        

client.pushMessage(PushoverMessage.builderWithApiToken("MY_APP_API_TOKEN")
        .setUserId("USER_ID_TOKEN")
        .setMessage("testing!")
        .build());

// push a message with optional fields
Status result = client.pushMessage(PushoverMessage.builderWithApiToken("MY_APP_API_TOKEN")
      .setUserId("USER_ID_TOKEN")
      .setMessage("testing!")
      .setDevice("device")
      .setPriority(MessagePriority.HIGH) // HIGH|NORMAL|QUIET
      .setTitle("title")
      .setUrl("https://github.com/sps/pushover4j")
      .setTitleForURL("pushover4j github repo")
      .setSound("magic")
      .build());
      
System.out.println(String.format("status: %d, request id: %s", result.getStatus(), result.getRequestId()));

// get and print out the list of available sounds:
for (PushOverSound sound : client.getSounds() ) {
    System.out.println(String.format("name: %s, id: %s", sound.getName(), sound.getId()));
}              
```


for the non-maven types, here are the required dependencies

* [pushover4j](http://github.com/sps/pushover4j/downloads)
* [gson 2.2.2](http://code.google.com/p/google-gson/downloads/list)
* [apache commons httpclient 4.2.1](http://hc.apache.org/downloads.cgi)