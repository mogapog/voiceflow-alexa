# Voiceflow-alexa
An extremely simple way of implementing voiceflow in an alexa skill. This skill works using the voiceflow dialog manager api, allowing for advanced ChatGPT conversations for free in alexa. Read carefully and do not change the names of _anything_ unless specified. Also make sure to hit save and then the build button in the alexa skill after finishing creating the intents, changing the invocation name or after you finish testing your skill successfully.

# Tutorial

## Voiceflow
![newflow](https://github.com/mogapog/voiceflow-alexa/assets/139735921/2e9e4520-6702-4685-9d28-0b52d7df6b57)

First, you want to make a voiceflow account and create an assistant. Then, you need to set up your assistant to something that looks similar to the photo above. The assistant will output a welcome message (that you can change to whatever you want), then capture all input and send it to an ai which will speak a response out loud and end the assistant. Currently, the assistant does not loop so everytime you want to ask a question you will have to start the skill again. Go into the integrations tab of your voiceflow assistant found on the side bar and copy your api key. Keep it stored, it will be important later.

## Alexa

![Header](https://github.com/mogapog/voiceflow-alexa/assets/139735921/c0a3733c-9e3f-4c82-ae00-e0d489a4ffef)

Log into your alexa account (the same amazon account you use for your alexa) and create a skill. Give it a name, language, etc. Select other as a type of experience and scroll down until you find the hosting settings. Select `Alexa hosted (Python)` and continue creating it. Make sure to change the invocation name of your skill after you create it too, in this case i am going to set it to `Alex Git` but you can set it to anything you want as long as it is within the amazon guidelines for invocation names.

### Hosting:
![Alexa hosted](https://github.com/mogapog/voiceflow-alexa/assets/139735921/2b5cff61-95cd-4276-b16c-8c398cd10ba8)

### Intents:

Create an intent called `InfoIntent` and give it a slot called `CatchAll` with the type `AMAZON.SearchQuery`. You can give it many different utterances (which are ways of activating the response), but all of them most follow the structure of: `'PHRASE' {CatchAll}`, by example: `Search for {CatchAll}`, or a keyword like `Example {CatchAll}`. Do keep in mind that `{CatchAll}` is the text that is going to be sent to the ai, so if you say `'Search for Domino's pizza'` and you have that as an utterance, the AI will only receive `Domino's pizza` as a prompt.

![infointent](https://github.com/mogapog/voiceflow-alexa/assets/139735921/4045cb04-a7d4-4fbe-8f25-45e951bd3a3b)
![catchall](https://github.com/mogapog/voiceflow-alexa/assets/139735921/6551a9c3-a6a1-4e72-a904-51080129bd02)

After that, get the latest release from [Releases](https://github.com/mogapog/voiceflow-alexa/releases) and upload the zip file that you downloaded to the `code` tab of your skill, as shown in the image below. Select every single folder of the zip file from the upload tab.

![Release](https://github.com/mogapog/voiceflow-alexa/assets/139735921/7d225290-1a4f-4f41-9795-395b0d5b8e90)

After that, replace `YOUR_API_KEY` in the code with your actual api key that you saved earlier from the voiceflow project. Remember to hit save and then deploy in your project after you finish updating the code.

![apikey](https://github.com/mogapog/voiceflow-alexa/assets/139735921/0eac2d50-4544-41c6-8345-dce50799a184)

### And you should be set!

# Conclusion and results

Now your code should work and you can test it in the `test` tab of your skill. For some reason, amazon does not let you test on some browsers like opera gx so i recommend using google chrome. Try it out with your browser of choice and see if it works. After you finish building your skill, if you used the same account on your echo device, you should be able to use it just by calling the invocation name that you set on your skill. Try waiting 20-30 minutes after building before testing on your echo device just to make sure it works.

![result](https://github.com/mogapog/voiceflow-alexa/assets/139735921/d68c1c4f-8c6d-426b-a553-4cd16cf8ca41)
