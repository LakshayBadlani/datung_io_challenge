# Data Science Take Home Assignment
Data Science Take Home Assignments used in Datung.IO recruitment process.

## Introduction

Welcome to Datung.IO's take-home assignment repository, part of our data science recruitment process. The following assignment will let you extract, explore and analyze audio data from English speaking male and females, and build learning models aimed to predict a given person's gender using vocal features, such as mean frequency, spectral entropy or mode frequency.

## Dataset

The raw data consists of, as of 30th August 2018, 95,481 audio samples of male and female speakers speaking in short English sentences. The raw data is compressed using `.tgz` files. Each `.tgz` compressed file contains the following directory structure and files:

- `<file>/`
  - `etc/`
    - `GPL_license.txt`
    - `HDMan_log`
    - `HVite_log`
    - `Julius_log`
    - `PROMPTS`
    - `prompts-original`
    - `README`
  - `LICENSE`
  - `wav/`
    - 10 unique `.wav` audio files

The total size of the raw dataset is approximately 12.5 GB once it has been uncompressed. The file format is `.wav` with a sampling rate of 16kHz and a bit depth of 16-bit. The raw dataset can be found **[here][2]**.

We recommend considering the following for your data pre-processing:

1. Automate the raw data download using web scraping techniques. This includes extraction of individual audio files. 
2. Pre-process data using audio signal processing packages such as [WarbleR](https://cran.r-project.org/web/packages/warbleR/vignettes/warbleR_workflow.html), [TuneR](https://cran.r-project.org/web/packages/tuneR/index.html), [seewave](https://cran.r-project.org/web/packages/seewave/index.html) for R, [librosa](https://librosa.org/doc/latest/index.html), [PyAudioAnalysis](https://github.com/tyiannak/pyAudioAnalysis) for Python, or similar packages for other programming languages
3. Consider, in particular, the [human vocal range][1], which typically resides within the range of **0Hz-280Hz**
3. To help you on your way to identify potentially interesting features, consider the following (non-exhaustive) list:
  - Mean frequency (in kHz)
  - Standard deviation of frequency
  - Median frequency (in kHz)
  - First quantile (in kHz)
  - Third quantile (in kHz)
  - Inter-quantile range (in kHz)
  - Skewness
  - Kurtosis
  - Mode frequency
  - Peak frequency
4. Make sure to check out all of the files in the raw data, you might find valuable data in files beyond the audio ones

  [1]: https://en.wikipedia.org/wiki/Voice_frequency#Fundamental_frequency
  [2]: http://www.repository.voxforge1.org/downloads/SpeechCorpus/Trunk/Audio/Main/16kHz_16bit/

## Question Set

The following are reference points that should be taken into account in the submission. Please use them to guide the reasoning behind the feature extraction, exploration, analysis and model building, rather than answer them point blank.

1. How did you go about extracting features from the raw data?
2. Which features do you believe contain relevant information?
  1. How did you decide which features matter most?
  2. Do any features contain similar information content?
  3. Are there any insights about the features that you didn't expect? If so, what are they?
  4. Are there any other (potential) issues with the features you've chosen? If so, what are they?
3. Which goodness of fit metrics have you chosen, and what do they tell you about the model(s) performance?
  1. Which model performs best?
  2. How would you decide between using a more sophisticated model versus a less complicated one?
4. What kind of benefits do you think your model(s) could have as part of an enterprise application or service?

## Submission

### Deadline

You have **7 days** to complete the assignment from the time that you have received the email containing the link to this GitHub repository.

> **Note:** Your submission will be judged with this timeframe in mind, and we do not expect the equivalent of a month's worth of work.

### Requirements

A written presentation, in **HTML or PDF format**, that clearly and succinctly walks us through your approach to extracting features, exploring them, uncovering any potential constraints or issues with the data in its provided form, your choice of predictive models and your analysis of the models' performance. Try to keep it concise. Please send your presentation (see *Requirements* below)to **charan [at] datung.io**, with it as an attachment, or provide us with a link to where you've uploaded your work.

Happy coding!

## Frequently Asked Questions

1. **Can I use &lt;Insert SDK or Framework here&gt; for the take home assignment?**
  > **Answer:** Yes, you are free to make use of the tools that you are most comfortable working with. We work with a mix of frameworks, and try to use the one best fit for the task at hand.
2. **Where do I send my assignment upon completion?**
  > **Answer:** You should have received an email with instructions about this take home assignment that led you to this repo. If you have been invited to the take home assignment, but haven't received an email, please email us at *charan[at]datung.io*.
3. **The raw data is too large to fit in memory, what do I do?**
  > **Answer:** This is part of the challenge, and the dataset is by design larger than can fit in memory for a normal computer. You will have to come up with a solution that enables processing of the data in a batch-like, or streaming, fashion, to extract meaningful features.
4. **Where do I send my presentation of my results?**
  > **Answer:** Please send it to **charan [at] datung.io**. In case you've uploaded your work somewhere else please provide a link that allows us to view it for evaluation.
