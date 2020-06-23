# Improving Segmentation for Technical Support Problems

<img src="https://aaai.org/Conferences/AAAI-19/wp-content/uploads/2018/11/ibm_research_ai.png" width="20%"> &nbsp; [![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)



This repository contains the data used in the paper:

**Improving Segmentation for Technical Support Problems** <br>
Kushal Chauhan and Abhirut Gupta <br>
*Proceedings of the 2020 Annual Conference of the Association for Computational Linguistics (ACL 2020)* <br>
[[arXiv](https://arxiv.org/abs/2005.11055)]  [[aclweb](https://www.aclweb.org/anthology/2020.acl-main.284/)]

<!-- [[Full Text]()] -->

<br>

### Abstract

Technical support problems are often long and complex. They typically contain user descriptions of the problem, the setup, and steps for attempted resolution. Often they also contain various non-natural language text elements like outputs of commands, snippets of code, error messages or stack traces. These elements contain potentially crucial information for problem resolution. However, they cannot be correctly parsed by tools designed for natural language. In this paper, we address the problem of segmentation for technical support questions. We formulate the problem as a sequence labelling task, and study the performance of state of the art approaches. We compare this against an intuitive contextual sentence-level classification baseline, and a state of the art supervised text-segmentation approach. We also introduce a novel component of combining contextual embeddings from multiple language models pre-trained on different data sources, which achieves a marked improvement over using embeddings from a single pre-trained language model. Finally, we also demonstrate the usefulness of such segmentation with improvements on the downstream task of answer retrieval.

<br>

### Data

The data is in `.csv` format with each row containing the complete span of a segment label in a ticket. The columns are described as follows:

- **TicketId**: Contains the [AskUbuntu](https://askubuntu.com/questions) question id. For example, the ticket in the dataset with TicketId `426166` can be found at https://askubuntu.com/questions/426166/.
- **SpanId**: Contains the unique id of the segment span in the dataset.
- **TextSpan**: Contains the string indices of the beginning and the end of the span in the format `[<begin>, <end>]` (both incusive).
- **Text**: Contains the text of the span.
- **Label**: Contains the segment label.

Example:

| TicketId | SpanId | TextSpan   | Text                | Label          |
| -------- | ------ | ---------- | ------------------- | -------------- |
| 426166   | 83     | [0, 16]    | I've already run    | O              |
| 426166   | 84     | [17, 26]   | free -t -m          | Command / Code |
| 426166   | 85     | [27, 31]   |  and                | O              |
| 426166   | 86     | [32, 49]   | ps aux --sort -rss  | Command / Code |

<br>

### Reference

If you find our data and methods useful, please cite:
```
@inproceedings{ticket-segmentation,
    title = {Improving Segmentation for Technical Support Problems},
    author = {Chauhan, Kushal  and Gupta, Abhirut},
    booktitle = {Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics},
    year = {2020},
    publisher = {Association for Computational Linguistics}
}
```

<br>

### License

This data is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

<br>

### Contact

This repository is maintained by Kushal Chauhan (kushalchauhan98@gmail.com) and Abhirut Gupta (abhirut.91@gmail.com).
