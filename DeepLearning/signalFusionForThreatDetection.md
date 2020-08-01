# [Deep Learning-based Fusion Of Behavior Signals For Threat Detection](https://www.microsoft.com/security/blog/2020/07/23/seeing-the-big-picture-deep-learning-based-fusion-of-behavior-signals-for-threat-detection/)

Applications of deep learning or machine learning methods to threat detection on endpoints, email, docs and apps. Within each domain, across domains, machine learning plays a critical role.

An isolated event is not a very good indication of malicious activity, but when augmented with several signals occurring at different times, the event can become a significant indicator of malicious activity.

### Classification model for wide-ranging data
detect malicious activities within massive amounts of data.
historical data with virtual process trees and signals of different types associated to these trees.

### Behavior-based and machine learning-based signals

- Behavior-based
    registry key, service start

- Machine learning-based
    machine learning model that produces signals on different pivots of a possible attack vector, a sequence of events.

### Data modeling
- Bag of words
    [3,0,1]
- Chronological
    [1,3,1,1]

### Deep CNN-BiLSTM

*Aim*: model long sequences of signals within the process tree to create high-level and localized features for the next layer of the network.

