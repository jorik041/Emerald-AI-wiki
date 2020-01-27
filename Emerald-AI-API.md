# Emerald AI API
Important (Read First): Emerald AI has tons of API that can be accessed to allow for added functionality, custom mechanics, and more. In order for these to be accessed via code, users must reference their AI’s EmeraldAISystem component. Once this is accessed, users will need to find the EmeraldAIEventsManager that holds all of the AI’s API. 
It is recommended that you use the EmeraldAI namespace at the top of your scripts to make accessing the Emerald AI scripts easier using:
```c#
using EmeraldAI;
```

Next, you will want a reference to an AI’s events manager script. There is one that is located on each AI. This can be done using the following and should be called on Start:

```c#
EmeraldAIEventsManager EventsManager = GetComponent<EmeraldAIEventsManager>();
```

Now, when using the EventsManager variable, you can access all of an AI’s internal functions that allow you to control a wide variety of functionality. The following API is assumed you used the EventsManager variable name as your reference to the EmeraldAIEventsManager component. 