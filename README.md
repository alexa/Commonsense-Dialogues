## Commonsense-Dialogues Dataset
  
We present Commonsense-Dialogues, a crowdsourced dataset of ~11K dialogues grounded in social contexts involving utilization of commonsense. The social contexts used were sourced from the **train** split of the [SocialIQA](https://leaderboard.allenai.org/socialiqa/submissions/get-started) dataset, a multiple-choice question-answering based social commonsense reasoning benchmark.

For the collection of the Commonsense-Dialogues dataset, each Turker was presented a social context and asked to write a dialogue of 4-6 turns between two people based on the event(s) described in the context. The Turker was asked to alternate between the roles of an individual referenced in the context and a 3rd party friend. See the following dialogues as examples:

```
    "1": {  # dialogue_id
        "context": "Sydney met Carson's mother for the first time last week. He liked her.",   # multiple individuals in the context: Sydney and Carson
        "speaker": "Sydney",   # role 1 = Sydney, role 2 = a third-person friend of Sydney
        "turns": [
            "I met Carson's mother last week for the first time.",
            "How was she?",
            "She turned out to be really nice. I like her.",
            "That's good to hear.",
            "It is, especially since Carson and I are getting serious.",
            "Well, at least you'll like your in-law if you guys get married."
        ]
    }

    "2": {
        "context": "Kendall had a party at Jordan's house but was found out to not have asked and just broke in.",
        "speaker": "Kendall",
        "turns": [
            "Did you hear about my party this weekend at Jordan\u2019s house?",
            "I heard it was amazing, but that you broke in.",
            "That was a misunderstanding, I had permission to be there.",
            "Who gave you permission?",
            "I talked to Jordan about it months ago before he left town to go to school, but he forgot to tell his roommates about it.",
            "Ok cool, I hope everything gets resolved."
        ]
    }

```

The data can be found in the `/data` directory of this repo. `train.json` has ~9K dialogues, `valid.json` and `test.json` have ~1K dialogues each. Since all the contexts were sourced from the **train** split of SocialIQA, it is imperative to note that any form of **multi-task** training and evaluation with Commonsense-Dialogues and SocialIQA must be done with caution to ensure fair and accurate conclusions.


Some statistics about the data are provided below:

|               Stat \ Split                   | Train | Valid | Test |
|                   ----                       | ----  | ----  | ---- |
|# of dialogues                                | 9058  | 1157  | 1158 |
|average # of turns in a dialogue              | 5.72  | 5.72  | 5.71 |
|average # of words in a turn                  | 12.4  | 12.4  | 12.2 |
|# of distinct SocialIQA contexts used         | 3672  | 483   |  473 |
|average # of dialogues for a SocialIQA context| 2.46  | 2.395 | 2.45 |


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This repository is licensed under the CC-BY-NC-4.0 License.

## Citation

If you use this dataset, please cite the following paper:

```
@article{zhoucommonsense,
  title={Commonsense-Focused Dialogues for Response Generation: An Empirical Study},
  author={Zhou, Pei and Gopalakrishnan, Karthik and Hedayatnia, Behnam and Kim, Seokhwan and Pujara, Jay and Ren, Xiang and Liu, Yang and Hakkani-Tur, Dilek},
  journal={SIGDIAL},
  year={2021}
}
```

Note that the paper uses newly collected dialogues as well as those that were filtered from existing datasets. This repo contains our newly collected dialogues alone.

