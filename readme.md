In this project, we'll be using AI technologies to make geospatial tools more accessible and easy to use.
Our dream would be an intelligent high-level interface that would allow a novice user to ask complex queries such as "show me all the wildfires currently burning in California, compare that to two weeks ago, predict how they will spread, and give me the results in a PDF."

Doing this requires solving three subproblems:
- Automated control of/interface with geospatial systems
- Orchestration of tools and workflows to generate complex results.
- Synthesis and description of the outputs of geospatial systems.

**Preliminaries:**

We'll be using Python in this project. If you're not familiar with Python, Pandas and NumPy.

Python [Fluent Python](https://learning.oreilly.com/library/view/fluent-python-2nd/9781492056348/)

Numpy  [NumPy documentation](https://numpy.org/learn/)

Pandas [Pandas documentation](https://pandas.pydata.org/docs/)

You should also be comfortable using [GitHub](https://www.github.com) and [HuggingFace](https://huggingface.co/)

If you are going to work with large models or complex analyses, you should also be familiar with running your code in the cloud, either via [Google Cloud](https://cloud.google.com/) or [Amazon Web Services](https://aws.amazon.com/).

**Geospatial Analysis**

We'll be building on top of existing ML systems for working with geospatial data. These systems are sometimes referred to as[foundation models](https://www.adalovelaceinstitute.org/resource/foundation-models-explainer/) - if you're not familiar with this term, please check out the linked explainer.

There are three foundation models that we'll be working with. They are:
- (Clay)[https://clay-foundation.github.io/model/index.html]
- (Prithvi)[https://huggingface.co/ibm-nasa-geospatial/Prithvi-100M]
- (Google Earth Engine)[https://earthengine.google.com/]

Please note that all of these systems are new and experimental. A learning outcome for this project is getting comfortable working with codebases that are new, not well-documented, and evolving.

**Large Language Models**

If you have not worked with an LLM in a programmatic fashion, before, you should install and get familiar with (Ollama)[https://ollama.com/blog]. This will help you get used to the idea of an LLM as an object that you can invoke methods on, as well as the basic parameters such as system prompt, context and temperature.

**Langchain** 

We'll use (LangChain)[https://www.langchain.com/langchain] and (LangGraph)[https://www.langchain.com/langgraph] to manage our workflows.

**Initial tasks:** 

Here are some warmup tasks to help you learn how to use each of these tools.

- (this tutorial)[https://huggingface.co/ibm-nasa-geospatial] shows how to fine-tune Prithvi to make three different kinds of *detectors*: a crop classifier, a burn scar detector, and a flood detector. Build your own detector using one of the other Geospatial datasets (found on HuggingFace)[https://huggingface.co/datasets?modality=modality:geospatial&sort=trending].

- (this tutorial)[https://github.com/Clay-foundation/model/blob/main/docs/tutorials/clay-v1-wall-to-wall.ipynb] Shows how to run Clay from end to end. Run both Clay and Prithvi. Where are they similar? Where do they differ? What assumptions does each package make?
The tutorial above shows how to detect fires in Portugal. Modify it to detect fires in Northern California.

- (this site)[https://developers.google.com/earth-engine/#api] Describes the Earth Engine API. (Here)[https://developers.google.com/earth-engine/tutorials/community/intro-to-python-api] is an intro tutorial. Modify it to get data in Fahrenheit from the USF campus.

**LLMs** 

- Now that we know how to write Clay and Prithvi scripts, can we use an LLM, along with either a RAG approach or a fine-tuning approach, to generate portions of a Clay or Prithvi script? 

- Once we have tools that can do this, we're ready to think about training an LLM to act as an agent. (This tutorial)[https://python.langchain.com/v0.1/docs/modules/agents/quick_start/] shows how to do this. Try to create an LLM-based agent that can run an existing tool. You might want to start with a simple command-line utility like date. 

- Now we want to use two or more agentic LLMs in a workflow. (LangGraph)[https://langchain-ai.github.io/langgraph/] is where we'll start. ((CrewAI)[https://github.com/crewaiinc/crewai] is a possible alternative.)

**User Interfaces**

- We also want a better way to work with this data. (The Chatbot interface is limited)[https://wattenberger.com/thoughts/boo-chatbots]. What would a next-gen UI for geospatial data look like? How do users currently work with tools like (ArcGIS)[https://www.arcgis.com/index.html]? This will involve talking with and surveying users and developing prototype UIs.

**Result summarization**

- Can we use an LLM to summarize the results of a Prithvi or Clay script? 

**Orchestration**

- As we start to add more agents and microservices, how can the be described in such a way that an orchestrating agent can find and compose them? 
