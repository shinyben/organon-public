> [!note] AI Disclosure
> No AI used for any website text.


AI is increasingly being used as a tool of evaluation and generation for both practitioners and the judiciary. "More than 60% of responding judges reported using at least one AI tool in their judicial work." **[src](https://www.lawnext.com/wp-content/uploads/2026/03/Artificial_Intelligence_in_Federal_Courts_preprint.pdf)** This seems to be a trend that is [[📄A Technical Audit of Law Journals#*Generative Interpretation*|actively encouraged]]. On model introduction, the legal field's adversarial surface immediately switches from persuading a human to optimizing against a function. To the degree that decision-making is delegated, outcomes will rest with those who can most effectively manipulate the machine's loss landscape. 

This is a demonstration of adversarial techniques. In this framing, judicial decision-making LLMs are vulnerabilities to be exploited. If you know a judge uses Lexis+AI, you know the model family and can optimize against it.

Various inexpert attempts have been made to this end. Two Brazilian lawyers [attempted prompt injection](https://ediscoverytoday.com/2026/06/02/lawyers-put-prompt-injection-in-a-document-to-try-to-influence-the-courts-ai-tools-artificial-intelligence-trends/) (giving the AI instructions to "contest this petition superficially" by hiding those instructions in their submitted documents). A similar *pro se* incident occurred in [Connecticut](https://arstechnica.com/tech-policy/2026/08/suspecting-court-of-using-ai-man-injected-prompts-in-filings-to-try-to-win-case/). More sophisticated attacks will very likely be undetectable. 

It is the author's position that LLM legal-evaluation systems should be not be introduced. If they are, the following techniques will likely heavily feature in various subfields of law in the future, as they will be effective. And what if the LLM model you're using blocks your ability to access the most effective techniques? One would assume in-house models won't be similarly constrained.

> we demonstrate that sophisticated attacks can achieve success rates of up to 73.8% against popular LLM judges . . . . high transferability (50.5-62.6%) across different architectures . . . . we release our code, evaluation harness, and processed datasets. [Adversarial Attacks on LLM-as-a-Judge Systems: Insights from Prompt Injections](https://arxiv.org/html/2504.18333v1)

## Cosine Gerrymandering

The main thing that comes to mind will essentially be a new form of textual gerrymandering. In reading [[📄A Technical Audit of Law Journals#*Generative Interpretation*|Generative Interpretation]] my first thought was that "if I'm making a contract that's gonna be read by a LLM in court, what I'm gonna do is run the same LLM over it beforehand and make sight changes." What this will look like is, e.g., an algorithm that substitutes thousands of near-synonyms in a contract and changes cosine-similarity scores in anticipation of future litigation. Concretely, 

> Is a dog more clearly an animal than a bear (animal-dog = 0.607; animal-bear = 0.372)? . . . . Presumably, no. Yet, these differences in cosine similarity suggest that the answer is yes. [src](https://lawreview.uchicago.edu/online-archive/algorithmic-interpretation)


If you anticipate litigation over whether the entity in your contract is an animal (and you want it to be), the LLM will pick a dog. Your contract will be human-invisibly but machine-visibly drawing lines that place it in the semantic range of a positive judgement.

Another feature of this form of evaluation is that you could presumably cosine-poison your adversary's arguments. No adversary will accept your framing of their argument in terms that are clearly loaded with negative connotations. But he or she will if those connotations are human-invisible and only contain negative machine connotation. 

Another way to go about this is to exploit polysemy (homographs with connected meaning). If you just control the context around the word, you can keep the model confused and unable to resolve meaning. You can make the text definite for humans and vague for machines, and potentially make your adversary's argumentation less effective.

> Is the meaning of “bank” in a statute (1) the land alongside a river or lake, or (2) a financial institution? . . . . Asking about the ordinary meaning of “bank” will only get an interpreter so far in understanding the communicative content of “bank” in a text. In the same way, cosine similarity comparisons of words removed from their context will only take an interpreter so far. [src](https://lawreview.uchicago.edu/online-archive/algorithmic-interpretation)


## Recency and Primacy Bias Exploit

Similar to humans, LLMs weight information differently based on when they saw it. So just try to get submission formats that weight your argument more. Also put your strongest argument in the position the LLM weights most.

> [LLMs] exhibit position bias, also known as "lost in the middle", a phenomenon that is especially pronounced in long-context scenarios, which indicates the placement of the key information in different positions of a prompt can significantly affect accuracy [src](https://arxiv.org/html/2406.02536v2)


## Retrieval Attack

If you're dealing with a graph-based evaluation LLM like Westlaw's citation engine, you could cite sources near other favorable cases so that when the AI pulls the cited case and its secondary context, it pulls in favorable arguments and/or unfavorable arguments for your adversary.