# Decoding Emergency Radio & Mapping Areas of Need
---

I am currently seeking both monetary and coding assistance in the effort. This project aims to be a mass data acquisition and data rendundancy tool for Humanitarian AI efforts. It will pull from multiple and simultaneous emergency radio sources, start and stop a recording process based on sound classification models, convert those audio streams into transcripts, use NLP and ML to extract address data, and then map those areas of need.

### Project Milestones:

- `Pull audio streams from multiple channels at once, using Flask as the backend and an OS-agnostic webView as the front end`
- `Test various neural network models with per sample, audio feature extraction data.`
- `Turn the audio arrays into blocks with manageable batch sizes to be fed to a STT service for transcripts.`
- `Use NLP techniques like NER and Regex, but feed them into a Naive Bayes model to determine address vs. not-address.`
- `Create an "intelligent" agent to clean and prepare the data for processing.`
- `Batch geocode.`
- `Map`

### Get Involved

Actively seeking technical insights, code snippets, and information leads to support a project initiation phase. This project is flying under the banner of Humanitarian AI, an amazing group based out of Cambridge, Massachusetts that is building data acquisition tools that are enormous in scope. That effort is currently being led by Brent Phillips.

## Background

##### This notebook started life as a `General Assembly` project, with contributions from myself, Patrick Cavins, Remy Shea, Maithili Joshi, Charles Rice, Matt Brems, and numerous other online educators, scientists, and coders.

Whenever there is a disaster, especially a large one where FEMA is involved, logistics can be overwhelming. During National and International emergencies it is crucial FEMA identify the areas in need. Not only does FEMA require an understanding of the nature of emergencies, they need to be able to map where those emergencies are taking place. Furthermore, it is imperative to provide failsafes and redundancies for crucial information such as emergency radio. That is why transcriptions and recordings are necessary. These are assumptions we will make for the sake of this project. 

A choice was made by the group to focus on one particular emergency radio system, for the sake of framing the problem, and though I was interested in a different approach, a Democratic choice was made, and in the end focusing on NIMS was a good enough start to begin the larger task of capturing data from any conceivable emergency radio system. 

After 9/11 FEMA helped establish the National Incident Management System. NIMS standardized protocols for emergency response dispatches, and the analysis done in this report will reveal some of those innerworkings. The majority of emergency radio systems are not in compliance, but this system will act as the starting point. The group decided to focus on Boone County, Missouri, as the testing location. It is small and uses modern NIMS dispatch methods. One of our group members at GA grew up nearby. Because NIMS emergency dispatch calls begin with identifiable alert tones, this was a good enough place to start building a proof of concept system that starts and stops a recording process using sound classification with DSP, converts those windows of audio into transcripts, and then uses NLP and an address vs. not address Naive Bayes model to identify addresses for mapping.

The value proposition for harnessing emergency dispatch data is substantial and noteworthy. The data made available through this code provides answers to important questions for FEMA:

- `Where are emergency services going? Patterns?`
- `Is there a need for data redundancy using STT and NLP in the case that other cataloging methods fail? During widespread power outages this become doubly important.`
- `Are the radio calls being converted to human-readable spreadsheets of data for lay people to analyze on common laptops or phones?`

The final application will be built using Flask and will leverage the Soundflower library to pull audio streams from up to 64 channels of emergency radio. This allows for far greater data acquisition times. I am also interested in using Docker to containerize the frameworks, various servers, service worker processes, and other dependencies so that anyone can swap my crappy code with stuff that is smarter. However, I am only a novice at Docker and feel like a lost lamb at the moment. Such an approach would allow the application to run from a local server on the computer or be used as a progressive web application (in time) that is smaller in size and connects to a remote server via satelite. This particular notebook is simply proof of concept. The application still needs to be built. Librosa and Parselmouth will be used for analysis and feature extraction.
