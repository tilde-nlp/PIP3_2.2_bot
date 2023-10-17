# PIP3_2.2_bot
This is the prototype created in activity 2.2 of the project "AI Assistant for Multilingual Meeting Management" (No. of the Contract/Agreement: 1.1.1.1/19/A/082).

Meeting management is provided using the Virtual Assistant created and edited through the Tilde Bot Dashboard. The .json files included in this site are exported from the Tilde Bot Dashboard and can be imported back to restore the Virtual Assistant.

The Virtual Assistant bot project on the Tilde Bot Dashboard consists of several parts:

- you can define entities that will be recognized in received text (files ![/entity/en-en.json](/entity/en-en.json) and ![/entity/lv-lv.json](/entity/lv-lv.json))
- you can provide utterance examples that are used for intent detector training (files ![/intent/en-en.json](/intent/en-en.json) and ![/intent/lv-lv.json](/intent/lv-lv.json))
- you can define dialog scenario according to which the conversation flow is managed, and appropriate answers prepared
- you can specify text strings for the output

Entities, utterance examples and output text strings in the Virtual Assistant project are prepared in several languages. The language of input is detected automatically, and the appropriate textual data are used for processing of input and preparation of answer.

When the Virtual Assistant receives the input it forwards it to the NLP components - Named Entity Recognition (NER) engine and Intent Recognition module.

