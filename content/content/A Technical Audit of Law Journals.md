Hi, I'm Ben, a 1L at UNC Law. In reading through contemporary legal scholarship, I've found that the technical details of AI are often misunderstood. Occasionally inferences are drawn from those misunderstandings that cascade into disastrous policy recommendations. 

Most notably this cascade has yielded 
- the largest removal of First Amendment protections ever advanced ([[A Technical Audit of Law Journals#*Speech Certainty: Algorithmic Speech and the Limits of the First Amendment*|Speech Certainty: Algorithmic Speech and the Limits of the First Amendment]])
- a tort liability regime that would allow LLM developers like OpenAI and Anthropic thwart strict liability in its entirety via a simple software update ([[A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]])

These findings prompted me to create this document of potential issues I've identified, meant to be readable for a general audience (though I have likely not explained something well enough on here and would be happy to hear suggestions for improvement). 

# Yale

## *Nondeterministic Torts: A Technical Approach to AI Liability* 
135 Yale L.J. 2719 (2026) [Source](https://yalelawjournal.org/note/nondeterministic-torts-a-technical-approach-to-ai-liability)

```
Who wrote it? - Yale Student Note
How objective is the issue? - Objective
How central is the issue to the article? - Central. The title itself is a reference to the technical issue
What's the outcome if the article is adopted - A tort regime for LLMs that tech firms can thwart with near-zero cost
```

I'm very proud of this paper, which involves an original mathematical proof that refutes the exact core premise of the Yale Note, as well as the introduction of Lipschitz continuity as a concept into legal scholarship (I had a friend at LexusNexus do a thorough check). 

L-continuity is the essential formal property that makes a product verifiably safe (or, currently, unsafe) at AI scale, and I expect it will be hard for law to handle the pacing problem (tech evolving faster than doctrine can regulate) in torts without reliance on it.

SSRN paste here ^b88360

# Harvard

## *Traditional and Computational Canons*
39 HARV. J.L. & TECH. 287 (2025) [Source](https://jolt.law.harvard.edu/assets/articlePDFs/v39.1/Traditional-and-Computational-Canons.pdf)

```
Who wrote it? - UChicago Law Instructor (previously MIT PhD in Cognitive Sci)
How objective is the issue? - Objective
How central is the issue to the article? - Not at all. It's also a cool paper. I mention this mainly to characterize [[A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]
What's the outcome if the article is adopted - The issue doesn't affect doctrinal recommendations
```

> Lower temperatures (e.g., 0) make outputs more deterministic, while higher temperatures (e.g., 1–2) make them more varied.

> A systematic sweep across nine values, ranging from fully deterministic (0) to maximally stochastic (2)

The paper characterizes temperature as a spectrum from "more" deterministic to more stochastic.  ^0f2b53



1. The axis is wrong. Stochasticity (variedness/randomness) is not the (true) opposite of determinism: nondeterminism is. While stochasticity is used as an antonym in standard ML usage, this shorthand is also technically wrong. Determinism is a property relative to a *specified* input set: a thing is deterministic "given input X." Properties of computer-generated randomness make it not truly random, and if we include that randomness as a specified input, even input stochasticity can yield determinism. This is something more attributable to the field's shorthand than the paper itself.
2. Something cannot be "more deterministic." Determinism is not a spectrum: it is a property of processes for which supplying the same inputs always produces the same outputs.[^1] This is also shorthand: what is likely meant by determinism is "lower-entropy / more-concentrated output distribution." 
3. High temperatures do not induce nondeterminism. This is a more complex explanation that I address in my reply to [[A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]

[^1]: *Non-Determinism and the Lawlessness of Machine Learning Code*, 2022 SYMP. ON COMPUT. SCI. & L. 1, 2-3. Cooper, Frankle, and De Sa (by logically inverting their definition of nondeterminism). [src](https://afedercooper.info/paper/cooper2022lawless.pdf)

## *Machine Rulemaking: Arbitrary and Capricious Review in the Age of AI*
138 Harv. L. Rev. 1821 (2025) [Source](https://harvardlawreview.org/print/vol-138/machine-rulemaking-arbitrary-and-capricious-review-in-the-age-of-ai/) 

```
Who wrote it? - Anonymous Harvard Student
How objective is the issue? - Objective
How central is the issue to the article? - It is the core of the article
What's the outcome if the article is adopted - Unsure, TODO: double check the Note's claim is represented correctly
```

> Traditional algorithms are deterministic... In contrast, an ML (machine learning) model can dynamically learn and adjust its approach as it is used

This is another determinism-related confusion, much like [[A Technical Audit of Law Journals#*Traditional and Computational Canons*|Traditional and Computational Canons]] and to a somewhat lesser degree [[A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]. Instead of mixing determinism with stochasticity as the Harvard JOLT Article does, this mixes determinism with "online algorithms," the property of an algorithm updating itself while it runs. An algorithm can be online and deterministic at the same time. While "dynamically learn" is of course definitionally restricted to learning systems, the learning aspect is not load-bearing in the context of the Note's claim - so the difference between "online learning" and "online" generally does not need to be addressed.

Machine learning models do not learn (does not update its parameters) or adjust as they are used. Once a model is trained, it generally does not update at all. ChatGPT and Claude models are fixed formulas and do not learn directly from users asking them questions. However the companies that develop them capture that user data and use it to train other models later.

The Note's central claim is that machine learning is uniquely hard for courts to review under §706(2)(A) because machine learning "evolves over time." Machine learning does not evolve over time in a way relevant to the Note's assertions. The Article's recommendations are then unfounded.

As an aside: online algorithms are also not a uniquely machine learning technique. There are simple examples in other fields. When you see a stock market graph with a smooth line imposed on top, that smooth line is, much of the time, the average of the last X price datapoints, known as a "simple moving average." This is an online algorithm. 

# Stanford

## *Speech Certainty: Algorithmic Speech and the Limits of the First Amendment*
Stan. L. Rev. 77 (2025) [Source](https://review.law.stanford.edu/wp-content/uploads/sites/3/2025/01/Austin-Levy-77-Stan.-L.-Rev.-1.pdf)

```
Who wrote it? - Two practitioners, both Stanford Law alums
How objective is the issue? - Subjective, but sometimes objective
How central is the issue to the article? - It is the core of the article
What's the outcome if the article is adopted - First Amendment protections are removed from the outputs of systems involving gradient descent, which is a much more sweeping ban than a targeted removal of protections for social media content moderation algorithms
```

> three fundamental characteristics of machine learning: (1) machine learning algorithms write their own rules; (2) machine learning programmers cannot explain those rules; and (3) the algorithms’ predictions are guaranteed to be wrong at least some of the time. Together, as we explore in Part IV, these characteristics prove decisive in the First Amendment analysis

However none of these things are correct in any way meaningful to the Article's objective.[^3] This was a hard one to address objectively because it is a technical claim using highly underspecified language. 

What is a rule? What does it mean for an algorithm to "write its own" rules when it itself is written by a programmer? What does "explain" mean? To whom? Using what resources? What level of explanation (e.g., "well it's because the numbers get multiplied together and they choose this word") is valid? None of these questions are fully addressed, and a number of citations (Pedro Domingos, Cade Metz) are, in the construction of these "fundamental characteristics," objectively used as substantiation for assertions they don't support.

SSRN paste here
# UChicago

## *Causal AI—A VISOR for the Law of Torts*
U. Chi. L. Rev. Online (2024) [Source](https://lawreview.uchicago.edu/online-archive/causal-ai-visor-law-torts)  

```
Who wrote it? - Humboldt University Law Professor
How objective is the issue? - Subjective
How central is the issue to the article? - Central. The title itself is a reference to the technical issue
What's the outcome if the article is adopted - There is no doctrinal recommendation as this is an article that simply predicts future outcomes. Low risk
```

> Causal AI is within reach.

The main issue is the quote 
> The frontier problem in the field of causal inference concerns the \[external\] variables . . . . If it were possible to rule out . . . that any variables that remained \[outside\] the model influence the \[internal\] variables in a way that distorts the . . . model . . . then causal analysis could be formalized and computerized in full." [^2]

To completely rule out external interference, you would first have to list every single potentially-confounding variable in the universe and prove it has zero impact. Because you cannot enumerate an infinite number of background factors, a causal model can never be perfectly sealed from the outside world. It is hard to envision this as a frontier problem - consensus seems to be that causal completeness is not mathematically decidable from data alone.

A second issue is that this "If X then Y" statement then being used as a lead-in for saying "This ***will*** mark a major step in the development of digital systems" and as the justification for the abstract's opener, "Causal AI is within reach." This is an unwarranted inductive leap from a hypothetical to a certainty.

Finally, SCM-exogenous variables (what I simplified to "external" variables) are misidentified, which may be the core of this paragraph. The paper says

> exogenous variables, these \[undefined\]\[ \]variables are excluded from causal models and treated as given.

Structural causal **models** actually *include* exogenous variables, but the modeled **system** *excludes* them. That is, the whole description of the world sees that they are there, but they aren't part of the core causal relationship described. 

What the reasoning in the paragraph relies on is *omitted/unmodeled* variables, not the variables the model already knows about and has chosen to set aside from causality and treat as given. It is much harder to rule out that all the infinite variables in the world don't impact your model than make that same judgement about the ones you already have in hand. Swapping them is what leads to this paragraph's seismic claim.

# Berkeley

## *AI’s Future May Be Quantum* (2026)
Berkeley Technology Law Journal (Blogpost) [Source](https://btlj.org/2026/02/ais-future-may-be-quantum/)

(The exposition questions aren't relevant here, it's a student blog explaining the landscape)

The article's

> qubits "can be 0 and 1 at the same time. That means a quantum computer can handle multiple calculations in parallel

is answered pretty directly by Scott Aaronson, Professor of Computer Science at UT Austin:

> The single most common misconception, which you find repeated in almost every popular article about the subject that is written says, well, a classical computer is made of bits, and so it can just try each possible solution one by one, but a quantum computer is made of qubits, which can be zero and one at the same time . . . . Well, that is gesturing towards something in the vicinity of the truth, but it’s also very seriously misleading. It leads people to think that quantum computers would have capabilities that actually we don’t think that they would have. This is not even controversial within this field, right. We all know this, but it’s very hard to get the message out. [src](https://www.ycombinator.com/blog/scott-aaronson-on-computational-complexity-theory-and-quantum-computers/?utm_source=chatgpt.com)

(specifically measurement collapses the superposition, so you need engineered constructive interference)

# UNC

## *Disability Discrimination by Clinical Algorithm*
N.C. L. Rev. 103 (2025) [Source](https://scholarship.law.unc.edu/nclr/vol103/iss1/5/) 

```
Who wrote it? - UW Law Professor, Indiana Law Professor
How objective is the issue? - Objective
How central is the issue to the article? - Hard to tell. It does undercut a very emphasized claim but there seems to be additional parallel evidence (interviews etc.) that make the same point
What's the outcome if the article is adopted - Low risk due to low centrality
```

> (n.128) the algorithm generated false positives eighty-nine percent of the time

This and and the claims around it swap the roles of precision, accuracy, and false positive rate. For example "accuracy of the algorithm eroded from 11%" seems to then use the same 89% "false positive" number as accuracy (since 100% - 89% = 11%). 

Far from being an 89% false positive rate, the source cited in this footnote says the rate is <1%. 

## *Deepfake Liability*
N.C. L. Rev. 104 (2026) [Source](https://scholarship.law.unc.edu/cgi/viewcontent.cgi?article=7066&context=nclr) 

```
Who wrote it? - Postdoc at the Hebrew University of Jerusalem, WashU Law Professor (Visiting), Penn Carey Law Professor
How objective is the issue? - Objective, large subjective
How central is the issue to the article? - The subjective is central
What's the outcome if the article is adopted - Only slight effectiveness 
```

The Article suggests, as one of three prescriptions
> requiring companies to only release their code under an open-source license prohibiting the removal of basic safeguards

However this suggestion goes against the [definition of open-source](https://opensource.org/osd) which says "The license must allow modifications and derived works" and "The license must not restrict anyone from making use of the program in a specific field of endeavor." A similar attempt a similarly "ethical license" has already been made and [shut down](https://github.com/raisely/NoHarm/pull/27#:~:text=TLDR%3A%20The%20%22Do,impossible%20to%20enforce.). Stable Diffusion, the main model that causes these issues, is already released under a non-open license that prohibits deep fakes - but it is still the main source of issues. It would be a minor edit to simply say "well then not open source" but that would cause problems for adoption: many enterprises can only work with open source. The prescription itself seems to need more grounding in the complexity of software licensing.

Another prescription is watermarking and relying on source code being difficult to edit (involving expertise). However a large subjective issue is raised here. The Article deals in "source code release" and never touches the important part: weight release. The model weights are out in the world, not just the code that generated the models. 

Stable Diffusion, for example, was a release of weights and weights-to-output code, not just source code. Weights being in the wild bypasses the need to edit source code (the expertise claim), since the weights are what a malicious actor would want to get from that source code anyway. Similarly, the watermarking (which gets optionally bolted onto the weights by the source code) is ineffective because the weights are out there in the wild, and weights on their own would need to have had the watermarks embedded via SynthID. And even this safeguard is ineffective because in-weight watermarks can be fine-tuned or purified out once weights are public.  The word "weight" does not come up at all in the article, despite weights being the central object of interest to third party developers. This seems to raise many questions.

# NeurIPS (Generally Understood to be the Best AI/ML Conference)

## *Prohibiting Generative AI in Any Form of Weapon Control* (2025)
39TH Conf. on Neural Info. Processing Sys [Source](https://neurips.cc/virtual/2025/loc/san-diego/poster/121921)

```
Who wrote it? - GMU Professor, (previously UVA Systems Engineering PhD, Duke Professorship)
How objective is the issue? - Objective
How central is the issue to the article? - I just read the technical part so I don't know
What's the outcome if the article is adopted - No idea 
```

This paper is cited in [[A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]. I say at fn.9 

> Cummings does not substantiate the Note’s key premise, though. Hers is a policy position paper, rather than an empirical paper seeking formal correctness. Read in context, it is not a substantiated claim that—literally interpreted—all connectionist AI models are neural networks, or that all neural networks are non-deterministic, or that no two outputs of the same input are ever the same. Such literal claims would contradict the Note’s other sources and are easily falsified.

Getting into her paper seemed too in the weeds for a student response, but I find my equivocation "not seeking formal correctness" to be incomplete. Her paper uses this sentence as setup
> Also known as neural networks, connectionist AI models are non-deterministic, meaning every time they are run, even with the same input, the outputs will be different

There are two important propositions in this sentence:
1. Connectionist AI models are non-deterministic
2. Every time non-deterministic networks are run, the outputs will be different

They are each incorrect: 
1. [[A Technical Audit of Law Journals#*Nondeterministic Torts A Technical Approach to AI Liability*|Nondeterministic Torts]]'s Response addresses this in depth
2. Outputs "will" be different means you will never get the same output. The paper should replace "will" with "can"

The paper also includes a graph that involves a spectrum of determinism, which is the same issue from the Harvard JOLT paper here [[A Technical Audit of Law Journals#^0f2b53]].

# Disclaimer

I'd like to generally disclaim that although I state things like "X is true," everything should be read with "it seems to me that X is true" or similar "I could definitely be wrong on this" asterisks being there in spirit

[^2]: The frontier problem in the field of causal inference concerns the exogenous variables and their bearing on the adequacy and completeness of causal models. If it were possible to rule out, with the help of computer-assisted mathematical analysis, that any variables that remained exogenous to the model influence the endogenous variables in a way that distorts the causal model, including its structural equations, then causal analysis could be formalized and computerized in full. Computers equipped with the necessary software could take over and extrapolate causal relationships from sets of observational data. Once digital machines understand the concept of causation, one can speak of Causal AI. This will mark a major step in the development of digital systems truly deserving the label of artificial intelligence. With an understanding of causation, many errors and hallucinations that are characteristic of the current generation of large language models *will* disappear. 

[^3]: (3) is correct but accuracy (being right) and certainty (being sure of your prediction) are mixed together in the Article's inferential step
