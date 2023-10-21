# Towards better understanding of COVID 19 misinformation flow using Artificial Intelligence based tools

This repository contains the public outputs of our project aimed at
better understanding of the conditions for sharing COVID 19
misinformation, in particular, what are the messages, which discourse
patterns they contain and which users are more likely to share the
messages.

Two papers are available as the output of the project:

``` example
@article{boumechaal23covid,
  title={Attitudes, Communicative Functions, and Lexicogrammatical features of Anti-Vaccine Discourse on Telegram},
  author={Souad Boumechaal and Serge Sharoff},
  journal={Applied Corpus Linguistics},
  volume=3,
  issue=3,
  year=2023,
  url = {http://corpus.leeds.ac.uk/serge/publications/2023-appied.pdf},
  publisher={Elsevier}
}
```

``` example
@inproceedings{sosa-sharoff-2022-multimodal,
    title = "Multimodal Pipeline for Collection of Misinformation Data from Telegram",
    author = "Sosa, Jose  and
      Sharoff, Serge",
    booktitle = "Proceedings of the Thirteenth Language Resources and Evaluation Conference",
    month = jun,
    year = "2022",
    address = "Marseille, France",
    publisher = "European Language Resources Association",
    url = "https://aclanthology.org/2022.lrec-1.159",
    pages = "1480--1489"
}
```

The repository for our pipeline for collection of multimodal information
from Telegram is at:
<https://github.com/josesosajs/telegram-data-collection>

# Project aims

We started with a pilot study to address a central problem of public
interpretation of scientific communication throughout the COVID-19
crisis. Scientific research is presented initially as evidence in peer
reviewed research papers, and then it is used to guide policy making
with the key facts and risks disseminated through various public
communication channels, such as parliamentary debates, government
policy, mass media, and social media. Part of the pilot study was
citizens' involvement through panel discussions which raised concerns
related to COVID-19 misinformation and its dire consequences on health.
Consequently, the pilot study evolved into the current project with the
aim of deploying Artificial Intelligence (AI) to identify demographic,
social, and political factors behind the increasing spread of COVID 19
misinformation on social media.

# Research Methodology

To train statistical models for predicting properties of social media
profiles sharing misinformation and the characteristics of shared
messages, we collected data about messages and accounts from Twitter,
Telegram, and Facebook. The data collection process started in August
2021 on a daily basis for a period of seven months. We used hashtags and
keywords to identify COVID related messages. Over this period, we
collected 1201582 tweets of which 140115 tweets were COVID-related.
Telegram data covered both text messages, images, and videos – with
955838 English messages and 40882 images.

The collected data was filtered and further analysed through a human
annotation process. This stage allowed us to highlight the topics
frequently discussed in COVID-related misinformation, and the
characteristics of the language used to construct compelling messages.
The annotation focused on understanding the intended meaning of messages
through identifying the choice of keywords, how they fuel certain
emotions and how they depict specific events such as lockdown, vaccines,
and Covid related measures. The annotators identified 7 common
categories that capture topics of 1742 annotated Twitter messages from
different points of time. These categories are: Anti-vaccine, Politics,
Conspiracy, Unreliable Scientific Sources, False Latest Update, Common
Concerns, Irrelevant.

A crucial part of the project was the authentic involvement of citizens
throughout the stages of the study. We held three discussion panels that
comprised a diverse representation of the population. The first two
panels were set up on November 9th, 2021. The aim of these sessions was
to explain the project aims to the participants and present them with
the data collected and annotated. The second panel took place on the
23<sup>rd</sup> of February 2022 in which preliminary results were
shared with the participants. These public engagements stimulated rich
discussions about factors shaping the topic of trust in misinformation.
The participants indicated that age, beliefs, and other psychological
factors such as emotive language might be a possible explanation for
trust in COVID misinformation. The citizens' perspectives were critical
throughout the various stages of the project as they informed the
development of the automatic prediction model.

# Key findings

## General communication

In the first part of the project, we have estimated the distribution of
topics across corpora, such as the COVID-19 Open Research Dataset
(CORD), government communication from the UK and US, British newspapers
(The Guardian, The Telegraph and The Sun), as well as general public
discussion in Twitter and Reddit.

| Source                         | Time span       | \#Texts    | \#Words     | AWL   |
|--------------------------------|-----------------|------------|-------------|-------|
| **Research papers:** CORD19    | 1922–2021       | 183,185    | 678,679,071 | 3,705 |
| **Authority sources:** CDC FAQ | 2020-08         | 645        | 29,375      | 46    |
| News from gov.uk               | 2020-01–2021-03 | 1,576      | 1,165,237   | 739   |
| **News reporting:** The Sun    | 2020-01–2021-03 | 21,704     | 14,724,045  | 678   |
| The Telegraph                  | 2020-01–2021-03 | 16,510     | 20,991,551  | 970   |
| The Guardian                   | 2020-01–2021-03 | 28,766     | 20,825,021  | 724   |
| World Economic Forum           | 2020-01–2021-03 | 2,528      | 2,440,099   | 965   |
| **Social Media:** Reddit       | 2020-02–2020-07 | 107,973    | 7,711,589   | 71    |
| Twitter                        | 2019-12–2021-01 | 30,016,828 | 688,073,844 | 23    |

Collected raw corpora

The topic model detects the prevalence of some topics, such as the use
of face masks, across the genres, while the sentiment classification
model demonstrates variation in the attitude towards such topics:

2010-09 The Annals of Occupational Hygiene  
*masks tested in the study had 40–90% instantaneous penetration levels
against polydisperse NaCl aerosols employed in the respirator test
protocol at 5.5 cm/s. Results show that common fabric materials may
provide marginal protection against nanoparticle-sized viruses.* →
`Function: academic, Face masks: not needed`

2020-04-20 NY Times  
*The C.D.C. has recommended that all Americans wear cloth masks if they
go out in public.* →
`Function: recommendation, Region: USA, Face masks: support`

2020-04-30 Gov.UK News  
*Today, we're publishing our PPE plan: being clear who needs PPE, when
they need it and who does not. … the best way to protect yourself and to
protect others is to regularly wash your hands. And of course the most
important way to protect yourself is to stay at home. Because a front
door is better than any face mask.* →
`Function: recommendation, Region: UK, Face masks: not needed`

2020-02-09, The Daily Telegraph  
*Increasing numbers of commuters on the London Underground are now
wearing face masks, twitchily keeping watch on the respiratory condition
of those around them.* →
`Function: reporting, Region: UK, Face masks: support`

2020-02-11, Twitter  
*I told yall I'm anti vaxx but I'm not stupid like the ppl in the world.
I'm the type who wears face masks when I'm in public.* →
`Function: opinion, Region: USA, Face masks: support`

2020-05-03 Reddit  
*With the lockdown being extended indefinitely, I'd like to have myself
personalised face masks, something more stylish and durable. Current set
of disposable masks don't last very long. Looking to support someone
local to South London.* →
`Function: request, Region: UK, Face masks: support`

## Misinformation

The automatic model considered the following parameters: Age, gender,
and far-right ideologies predicted from accounts, while topic, emotional
content, true/false information, functional style, vagueness, and
far-right ideologies were predicted from text messages. The classifiers'
statistical findings show that the demographic factor is crucial in
COVID misinformation flow. First, users aged between 35 and 54 years
share more false information, whereas those under 25 share very little
misinformation. Gender (Female, Male, Brand) was classified in relation
to COVID misinformation messages. This correlation reveals that males
share significantly more false information than females and brands. We
presented this finding with the research participants in the second
citizen panel (23<sup>rd</sup> February 2022) to seek their views. The
participants suggested that isolation, accessibility, fear and the
source of information also shape how people from certain age groups
trust the content they are exposed to on social media.

Given the importance of the geographic location to how the global
pandemic was experienced and contained. The automatic classifier
identified the US (United States) and the UK (United Kingdom) at the top
of the list followed by India, Canada and South Africa. To further
examine the impact of beliefs on COVID misinformation flow, data about
political ideology, in particular, far-right thinking was trained to
develop a classifier. The results of the predictions show that
far-right-leaning accounts share more COVID misinformation. Correlating
this prediction with the topic classifier further demonstrates that
vaccine misinformation tends to be promoted by far-right accounts.

Other interesting findings relate to the content of the message
characterising COVID misinformation circulating on social media
platforms. The automatic classifier related to style indicates that
misinformation on social media uses a particular strategy of writing.
For persuasive effects, the functional style of misinformation is more
frequently expressed in fake academic writing or as mythical narrative
stories.
