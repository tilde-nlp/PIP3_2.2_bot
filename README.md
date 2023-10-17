# PIP3_2.2_bot
This is the prototype created in activity 2.2 of the project "AI Assistant for Multilingual Meeting Management" (No. of the Contract/Agreement: 1.1.1.1/19/A/082).

Meeting management is provided using the Virtual Assistant created and edited through the Tilde Bot Dashboard. The .json files included in this site are exported from the Tilde Bot Dashboard and can be imported back to restore the Virtual Assistant.

The Virtual Assistant bot project on the Tilde Bot Dashboard consists of several parts:

- you can define entities that will be recognized in received text (files ![/entity/en-en.json](/entity/en-en.json) and ![/entity/lv-lv.json](/entity/lv-lv.json))
- you can provide utterance examples that are used for intent detector training (files ![/intent/en-en.json](/intent/en-en.json) and ![/intent/lv-lv.json](/intent/lv-lv.json))
- you can define dialog scenario according to which the conversation flow is managed, and appropriate answers prepared (file ![/model.json](/model.json))
- you can define actions that are used in scenario to get or process some data, for example, calling Javascript function or the Web Service  (file ![/actions.json](/actions.json))
- you can specify text strings for the output (files ![/lang/en-en.json](/lang/en-en.json) and ![/lang/lv-lv.json](/lang/lv-lv.json))

The general settings of the Virtual Assistant are specified in the file ![/settings.json](/settings.json)

Entities, utterance examples and output text strings in the Virtual Assistant project are prepared in several languages. The language of input is detected automatically, and the appropriate textual data are used for processing of input and preparation of answer.

When the Virtual Assistant receives the input it forwards it to the NLP components - Named Entity Recognition (NER) engine and Intent Recognition module.

## Intents

The Virtual Assistant recognizes 3 intents:

- intent *hello*, represented by such utterances as 'hi there', 'hello bot', 'good morning', etc.
- intent *bye*, represented by such utterances as 'see you later', 'goodbye', 'see you tomorrow', etc.
- intent *help*, represented by such utterances as 'do you hear me', 'tell me what you can do', 'to what questions you can answer', etc.

## Entities

The Virtual Assistant recognizes 12 types of entities:

- type *Person_name* - different first names
- type *Speaker* - regular expression with two words starting with a capital letter
- type *Com_nextmeeting* - words 'nextmeeting' or 'meeting'
- type *Prompt* - regular expression containing words 'Tilde', 'please', and 'write' or 'note' or 'task' or 'decision'
- type *Language* - regular expression containing name of a language
- type *Commands* - regular expression containing different commands
- type *Com_decision* - word 'decision'
- type *Com_task* - word 'task'
- type *Com_stop* - word 'stop'
- type *Com_download* - word 'download'
- type *Com_sr_lang* - words 'SR language'
- type *Com_display_lang* - words 'display language'

## Commands

The Meeting Management Application that works through the Microsoft Teams interface communicates with the Virtual Assistant in order to detect the certain commands and to provide an appropriate answer.

The following commands are implemented:

- command *Next meeting*

For meeting scheduling the entities of type *Prompt* and *Com_nextmeeting* are used. The regular expression captures the text after the initial phrase that contains the time of the next meeting. The answer contains the prefix ‘NEXT MEETING:’ and the passed in utterance.

![/nextmeeting.jpg](/nextmeeting.jpg)

- command *Decision*

To use this command user needs to include in the utterance entities of type *Prompt* and *Com_decision*. The answer contains the prefix ‘DECISION:’ and the passed in utterance.

![/decision.jpg](/decision.jpg)

- command *Task*

To use this command user needs to include in the utterance entities of type *Prompt* and *Com_task*. The answer contains the prefix ‘TASK:’ and the passed in utterance.

![/task.jpg](/task.jpg)


