> [!note] AI Disclosure
> No AI used for any website text.
> 
> The Yale paper used AI that conformed with both the *GenAI for the Legal Profession* course from Berkeley Law and Yale Law Journal's requirements. Similar with the (in-progress) Stanford paper.

Hi, I'm Ben, a 1L at UNC Law. In reading through contemporary legal scholarship, I've found that the technical details of AI/ML are often misunderstood. Occasionally inferences drawn from those misunderstandings cascade into flawed policy recommendations. I've kept my comments on the legal side of these combined legal/technical papers to a minimum.

Most notably this cascade has yielded 
- what would be the largest removal of First Amendment protections ever advanced ([[📄A Technical Audit of Law Journals#*Speech Certainty: Algorithmic Speech and the Limits of the First Amendment*|Speech Certainty: Algorithmic Speech and the Limits of the First Amendment]])
- a tort liability regime that would allow LLM developers like OpenAI and Anthropic to thwart strict liability in its entirety via a simple software update ([[📄A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]])
- a recommendation that judges resolve the ordinary meaning of words with mathematical techniques that have no substantive meaning ([[📄A Technical Audit of Law Journals#*Generative Interpretation*|Generative Interpretation]] - though I later found someone else had already written a similar critique)

These findings prompted me to make public this document of potential issues I've identified, meant to be readable by a general audience (though I have likely not explained everything well and would be happy to hear suggestions for improvement). 

## *Nondeterministic Torts: A Technical Approach to AI Liability* 
135 Yale L.J. 2719 (2026) [Source](https://yalelawjournal.org/note/nondeterministic-torts-a-technical-approach-to-ai-liability)

> [!note] Article Metadata
> - **Who wrote it?** — Yale Student Note
> - **How objective is the issue?** — Objective
> - **How central is the issue to the article?** — Central. The title itself is a reference to the technical issue
> - **Outcome if the article is adopted** — A tort regime for large language models (LLMs) that tech firms can thwart with near-zero cost

I'm very proud of this paper, which involves an original mathematical proof that refutes the exact core premise of the Yale Note, as well as the introduction of Lipschitz continuity as a concept into legal scholarship (I had a friend at LexusNexis do a thorough check). 

The easiest communication of the issue at the core of the paper is the fact that its citations contradict it. From my Response:

> The Note cites a short list of technical sources to support its claims that, in LLMs, “precise determinism is not possible” . . . . the Note relies on [Cooper, Frankle, and De Sa](https://arxiv.org/pdf/2206.11834), but they explain that “A particular model . . . is deterministic—always producing the same output given the same input.” (quote on page 3)

L-continuity, where I end up, is the essential formal property that makes a product verifiably safe (or, currently, unsafe) at AI scale, and I expect it will be hard for law to handle the pacing problem (tech evolving faster than doctrine can regulate) in torts without reliance on it. I mean this in the sense that certain aspects of the pacing are treated as contingently hard, or "hard for now" ("we just don't have enough data yet") and L-continuity constitutes proof that no amount of data will give a solution. Treating certain problems as temporary gaps when they are in fact provably unsolvable is just wasting time and effort, and delays the necessary doctrinal response (e.g. the suggested strict liability for materially untested systems).

[Paper on SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7220898)^b88360

![[THERE IS SUCH THING AS A TAME BEAR - SSRN v0.pdf]] ^7a5bda

### *Traditional and Computational Canons*
39 HARV. J.L. & TECH. 287 (2025) [Source](https://jolt.law.harvard.edu/assets/articlePDFs/v39.1/Traditional-and-Computational-Canons.pdf)

> [!note] Article Metadata
> - **Who wrote it?** — UChicago Law Instructor (previously MIT PhD in Cognitive Sci)
> - **How objective is the issue?** — Objective
> - **How central is the issue to the article?** — Not at all. It's also a cool paper. I mention it mainly because it shows how mixing compsci's shorthand and law's language-literalism could have downstream effects (eg Nondeterministic Torts)
> - **Outcome if the article is adopted** — The issue doesn't affect doctrinal recommendations

> Lower temperatures (e.g., 0) make outputs more deterministic, while higher temperatures (e.g., 1–2) make them more varied.

> A systematic sweep across nine values, ranging from fully deterministic (0) to maximally stochastic (2)

The paper characterizes temperature as a spectrum from "more" deterministic to more stochastic.  


1. The axis is wrong. Stochasticity (variedness/randomness) is not the (true) opposite of determinism: nondeterminism is. While stochasticity is used as an antonym in standard ML usage, this shorthand is also technically wrong. Determinism is a property relative to a *specified* input set: a thing is deterministic "given input X." Properties of computer-generated randomness make it not truly random, and if we include that randomness as a specified input, even input stochasticity can yield determinism. This is something more attributable to the field's shorthand than to the paper itself.
2. Something cannot be "more deterministic." Determinism is not a spectrum: it is a property of processes for which supplying the same inputs always produces the same outputs.[^1] This is also shorthand: what is likely meant by determinism is "lower-entropy / more-concentrated output distribution." ^0f2b53
3. High temperatures do not induce nondeterminism. This is a more complex explanation that I address in my reply to [[📄A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]

[^1]: *Non-Determinism and the Lawlessness of Machine Learning Code*, 2022 SYMP. ON COMPUT. SCI. & L. 1, 2-3. Cooper, Frankle, and De Sa (by logically inverting their definition of nondeterminism). [src](https://afedercooper.info/paper/cooper2022lawless.pdf)

### *Machine Rulemaking: Arbitrary and Capricious Review in the Age of AI*
138 Harv. L. Rev. 1821 (2025) [Source](https://harvardlawreview.org/print/vol-138/machine-rulemaking-arbitrary-and-capricious-review-in-the-age-of-ai/) 

> [!note] Article Metadata
> - **Who wrote it?** — Anonymous Harvard Student
> - **How objective is the issue?** — Objective
> - **How central is the issue to the article?** — It is the core of the article
> - **Outcome if the article is adopted** — Unsure, I'm looking at this further after [[📄A Technical Audit of Law Journals#*Speech Certainty Algorithmic Speech and the Limits of the First Amendment*|Speech Certainty]]

> Traditional algorithms are deterministic... In contrast, an ML (machine learning) model can dynamically learn and adjust its approach as it is used

This is another determinism-related confusion, much like [[📄A Technical Audit of Law Journals#*Traditional and Computational Canons*|Traditional and Computational Canons]] and to a somewhat lesser degree [[📄A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]. Instead of mixing determinism with stochasticity as the Harvard JOLT Article does, this mixes determinism with "online algorithms," the property of an algorithm updating itself while it runs. An algorithm can be online and deterministic at the same time. While "dynamically learn" is of course definitionally restricted to learning systems, the learning aspect is not load-bearing in the context of the Note's claim - so the difference between "online learning" and "online" generally does not need to be addressed.

Machine learning models do not learn (do not update their parameters) or adjust as they are used. Once a model is trained, it generally does not update at all. ChatGPT and Claude models are fixed formulas and do not learn directly from users asking them questions. However the companies that develop them capture that user data and use it to train other models later.

The Note's central claim is that machine learning is uniquely hard for courts to review under §706(2)(A) because machine learning "evolves over time." Machine learning does not evolve over time in a way relevant to the Note's assertions. Its recommendations are then unfounded.

As an aside: online algorithms are also not a uniquely machine learning technique. There are simple examples in other fields. When you see a stock market graph with a smooth line imposed on top, that smooth line is, much of the time, the average of the last X price datapoints, known as a "simple moving average." This is an online algorithm. 

### *Beyond Infringement: Rethinking DMCA § 1202 for Generative AI*
78 STAN. L. REV. 667 (2026)

> LLMs create distinct, independent outputs for each user.

The paper then cites nondeterminism ([[📄A Technical Audit of Law Journals#*An Empirical Study of the Non-determinism of ChatGPT in Code Generation*|below]]) as proof. However nondeterminism (one input can generate more than one output) is not the same as independent outputs (each new input receives a newly-generated output). Independent outputs and determinism could exist and the paper's point would still hold. This Note looked very well thought out.

### *An Empirical Study of the Non-determinism of ChatGPT in Code Generation*
arXiv:2308.02828 [cs.SE] (2023) [src](https://arxiv.org/pdf/2308.02828)

> [!note] Article Metadata
> Computer science paper cited in [[📄A Technical Audit of Law Journals#*Beyond Infringement Rethinking DMCA § 1202 for Generative AI*|Beyond Infringement]]

> Large Language Models (LLMs) are nondeterministic by nature

LLMs are deterministic by nature. See [[📄A Technical Audit of Law Journals#^7a5bda]]


### *Generative Interpretation*
99 N.Y.U. L. REV. 451 (2024) [src](https://nyulawreview.org/wp-content/uploads/2024/05/99-NYU-L-Rev-451-1.pdf)

> [!note] Article Metadata
> NOTE: After looking into this more and trying to figure out if I could get a paper out of it, I found out that Grimmelmann, Sobel & Stein, _Generative Misinterpretation_, 63 Harv. J. on Legis. (2026) already nearly makes the critique that I suggested. This makes any paper I could write more nitpicky than helpful. I'm leaving it up due to my independent derivation.
> 
> - **Who wrote it?** — UPenn Carey Law Professor, U Alabama Law Professor
> - **How objective is the issue?** — Objective
> - **How central is the issue to the article?** — It is the core of the article
> - **Outcome if the article is adopted** — Judges feel justified in establishing "ordinary meaning" of words in contracts off inferences that have no substantive grounding 

> models can be set to be hotter (more random) or colder (more deterministic)

Same thing as [[📄A Technical Audit of Law Journals#*Machine Rulemaking Arbitrary and Capricious Review in the Age of AI*|Machine Rulemaking]]

This is a super quick sketch of a broader problem with the paper:

It feels like the paper is saying "oh we can figure out what contract terms mean by asking an AI and if it gives us some high-percent answer that can be used towards ordinary meaning in the same way a survey can." But if you want to replace population surveys with LLM output it feels like it should be established that LLM outputs are actually good proxies for survey results and I'm not seeing any comment on that in the paper. Surveys are flawed for the reasons they mention but have at least some claim to validity in their sampling of the population, whereas LLMs are completely ungrounded (their output is more about what they were trained on than true population-sampling) even if we do show surveys and LLMs agree a lot. 

So it sounds like we're getting (some) judges using AI to decide stuff already and the paper wants to put some guardrails on that but the whole enterprise of establishing that AI outputs are empirically grounded seems pretty questionable but judges are doing it anyway and need some justification(?) or correction by reducing judicial reliance on priors, but that leaves the actual issue of judicial reliance on quasi-empiric outputs a bit untouched. 

It doesn't seem established that LLMs have *any* relationship to ordinary meaning but when the judiciary uses LLM output to eg enter summary judgment it making an ordinary meaning call based on an algorithm that hasn't been shown to have anything to do with ordinary meaning. 

The validity of the paper's use of cosine similarity as the same as survey results has issues as well - cosine similarity measures how often the two terms *appear in similar contexts* in the *entire* training data. What we want to know is whether the two terms are *interpreted* similarly *given some context C.* This is extremely gameable - just saturate your contract with terms with different general-meaning and expert-meaning words like "consideration" that would lead to the evaluation tilting in your favor.

> Now, the model doesn’t provide (nor could it) a scientific answer
	to the question of whether certain words are sufficiently close to make
	the plain meaning of flood unambiguous. That choice is ultimately a
	normative one which judges must make. But there is a bit of difference
	between an informed conclusion based on a statistical analysis of billions
	of texts and a judgment by a few dictionary editors. And there is an ocean
	of difference between the baroque and expensive textualism the court
	used and code that is cheap, replicable, quick, and most importantly,
	extremely straightforward to use. Simply put, generative interpretation
	is good enough for many cases that currently employ more expensive,
	and arguably less certain, methodologies. It’s a workable, workmanlike
	method for a resource-constrained contract litigation world.
## *Speech Certainty: Algorithmic Speech and the Limits of the First Amendment*
Stan. L. Rev. 77 (2025) [Source](https://review.law.stanford.edu/wp-content/uploads/sites/3/2025/01/Austin-Levy-77-Stan.-L.-Rev.-1.pdf)

> [!note] Article Metadata
> - **Who wrote it?** — Two practitioners, both Stanford Law alums
> - **How objective is the issue?** — Subjective, but sometimes objective
> - **How central is the issue to the article?** — It is the core of the article
> - **Outcome if the article is adopted** — First Amendment protections are removed from the outputs of systems involving gradient descent, which is a much more sweeping ban than a targeted removal of protections for social media content moderation algorithms

> three fundamental characteristics of machine learning: (1) machine learning algorithms write their own rules; (2) machine learning programmers cannot explain those rules; and (3) the algorithms’ predictions are guaranteed to be wrong at least some of the time. Together, as we explore in Part IV, these characteristics prove decisive in the First Amendment analysis

However none of these things are correct in any meaningful way regarding the Article's objective.[^3] This was a hard one to address objectively because it is a technical claim using highly underspecified language. 

What is a rule? What does it mean for an algorithm to "write its own" rules when it itself is written by a programmer? What does "explain" mean? To whom? Using what resources? What level of explanation (e.g., "well it's because the numbers get multiplied together and they choose this word") is valid? None of these questions are fully addressed, and a number of citations (Pedro Domingos, Cade Metz) are, in the construction of these "fundamental characteristics," objectively used as substantiation for assertions they don't support.

Pasting from the unfinished paper:

> [!NOTE] 
> The Article’s entire distinction between traditional code and machine learning rests on a single phrase: that machine learning algorithms “write their own rules.” The phrase appears in the abstract, anchors the Introduction, and serves as a pillar to argumentation throughout. Yet the Article never substantiates it, because the sources it cites do not support the Article’s claim.
> 
> The two authorities are quoted accurately, but make narrower statements than the Article needs. Pedro Domingos, writing for a general audience, says that “[l]earning algorithms . . . are algorithms that make other algorithms.” That is, one program, written by a human, can produce a second (likely simpler) program. Domingos’ claim that *some* machine learning algorithms *can* produce *other* algorithms does not establish what the Article requires to show machine learning's universal self-authorship: that *all* machine learning algorithms *do* author *themselves*. 
> 
> Similarly, the Article’s *Wired* feature quotes a former Google engineer saying that with machine learning “we don’t have to write *these* rules anymore.” This engineer is best understood to say that Google’s old hand-written search rules were being replaced with machine learning, not that the company's engineers have stopped authoring its search algorithms altogether, and can’t be used as the Article uses it to demonstrate any machine self-authorship of rules. 
> 
> Both sources are popularizations, never meant to bear technical—much less constitutional—weight. No search through the appropriate source, technical literature, will yield sources that hold that a trained model is authorless, because it is not.

TODO: SSRN paste here
## *Causal AI—A VISOR for the Law of Torts*
U. Chi. L. Rev. Online (2024) [Source](https://lawreview.uchicago.edu/online-archive/causal-ai-visor-law-torts)  

> [!note] Article Metadata
> - **Who wrote it?** — Humboldt University Law Professor
> - **How objective is the issue?** — Subjective
> - **How central is the issue to the article?** — Central. The title itself is a reference to the technical issue
> - **Outcome if the article is adopted** — There is no doctrinal recommendation as this is an article that simply predicts future outcomes. Low risk

> Causal AI is within reach.

The main issue is the quote 
> The frontier problem in the field of causal inference concerns the \[external\] variables . . . . If it were possible to rule out . . . that any variables that remained \[outside\] the model influence the \[internal\] variables in a way that distorts the . . . model . . . then causal analysis could be formalized and computerized in full." [^2]

To completely rule out external interference, you would first have to list every single potentially-confounding variable in the universe and prove it has zero impact. Because you cannot enumerate an infinite number of background factors, a causal model can never be perfectly sealed from the outside world. It is hard to envision this as a frontier problem - consensus seems to be that causal completeness is not mathematically decidable from data alone.

A second issue is that this "If X then Y" statement then being used as a lead-in for saying "This ***will*** mark a major step in the development of digital systems" and as the justification for the abstract's opener, "Causal AI is within reach." This is an unwarranted inductive leap from a hypothetical to a certainty.

Finally, SCM-exogenous variables (what I simplified to "external" variables) are misidentified, which may be the core of this paragraph. The paper says

> exogenous variables, these \[undefined\]\[ \]variables are excluded from causal models and treated as given.

Structural causal **models** actually *include* exogenous variables, but the modeled **system** *excludes* them. That is, the whole description of the world sees that they are there, but they aren't part of the core causal relationship described. 

What the reasoning in the paragraph relies on is *omitted/unmodeled* variables, not the variables the model already knows about and has chosen to set aside from causality and treat as given. It is much harder to rule out impact from all the infinite variables in the world than it is to make that same judgment about the ones you already have in hand. Swapping them is what leads to this paragraph's seismic claim.

## *AI’s Future May Be Quantum* 
Berkeley Technology Law Journal (Blogpost) (2026) [Source](https://btlj.org/2026/02/ais-future-may-be-quantum/)

(The exposition questions aren't relevant here, it's a student blog explaining the landscape)

The article's

qubits
> can be 0 and 1 at the same time. That means a quantum computer can handle multiple calculations in parallel

is answered pretty directly by Scott Aaronson, Professor of Computer Science at UT Austin:

> The single most common misconception, which you find repeated in almost every popular article about the subject that is written says, well, a classical computer is made of bits, and so it can just try each possible solution one by one, but a quantum computer is made of qubits, which can be zero and one at the same time . . . . Well, that is gesturing towards something in the vicinity of the truth, but it’s also very seriously misleading. It leads people to think that quantum computers would have capabilities that actually we don’t think that they would have. This is not even controversial within this field, right. We all know this, but it’s very hard to get the message out. [src](https://www.ycombinator.com/blog/scott-aaronson-on-computational-complexity-theory-and-quantum-computers/?utm_source=chatgpt.com)

(specifically, measurement collapses the superposition, so you need engineered constructive interference)

## *Retrieval-Augmented Generation: Structurally Enabling Reliable AI Output*
10 Geo. L. Tech. Rev. 414 (2025) [Source](https://georgetownlawtechreview.org/retrieval-augmented-generation-structurally-enabling-reliable-ai-output/GLTR-07-2026/)

> [!note] Article Metadata
> - **Who wrote it?** — Associate at Kirkland & Ellis
> - **How objective is the issue?** — Objective
> - **How central is the issue to the article?** — Total. The title's claim *is* the technical error
> - **Outcome if the article is adopted** — Courts and bar authorities treat RAG-based research tools as structurally reliable for Rule 11, when they are not reliable 

The paper:

> Because the "knowledge" is sitting right in front of the model, the LLM no longer needs to "guess" the next word based on probability. Instead, it engages in "grounding," where the LLM will treat the specified text as the ground truth.

Computer science research:

> Recently, certain legal research providers have touted methods such as retrieval-augmented generation (RAG) as "eliminating" (Casetext, 2023) or "avoid[ing]" hallucinations (Thomson Reuters, 2023), or guaranteeing "hallucination-free" legal citations (LexisNexis, 2023) . . . . we find that the AI research tools made by LexisNexis (Lexis+ AI) and Thomson Reuters (Westlaw AI-Assisted Research and Ask Practical Law AI) each hallucinate between 17% and 33% of the time[^5]

So the LLM still guesses. It just guesses with the "knowledge" directly accessible. In other words, RAG changes what is in the context window.[^4] It does not touch the process of probability-based next-word generation. This refutes the core of the Note.

There are also a number of supporting confusions. "[A]pplying the law of large numbers, an LLM's output represents a probabilistic average of the knowledge": autoregressive decoding is neither averaging nor sampling from a fixed distribution. Another, "the LLM does not store the original document's details, but extracts the statistical pattern of the text and discards the rest to make the model small enough to run on a server" is wrong[^7][^8] and cites to the Harvard Digest piece, but the cited source does not comment on the topic at all.

## *Deepfake Liability*
N.C. L. Rev. 104 (2026) [Source](https://scholarship.law.unc.edu/cgi/viewcontent.cgi?article=7066&context=nclr) 

> [!note] Article Metadata
> - **Who wrote it?** — Postdoc at Hebrew University of Jerusalem; WashU Law Professor (Visiting); Penn Carey Law Professor
> - **How objective is the issue?** — Objective, with large subjective secondary
> - **How central is the issue to the article?** — The subjective is central
> - **Outcome if the article is adopted** — Only slight effectiveness

The Article suggests, as one of three prescriptions
> requiring companies to only release their code under an open-source license prohibiting the removal of basic safeguards

However this suggestion goes against the [definition of open-source](https://opensource.org/osd) which says "The license must allow modifications and derived works" and "The license must not restrict anyone from making use of the program in a specific field of endeavor." A similar attempt at a similarly "ethical license" has already been made and [shut down](https://github.com/raisely/NoHarm/pull/27#:~:text=TLDR%3A%20The%20%22Do,impossible%20to%20enforce.). Stable Diffusion, the main model that causes these issues, is already released under a non-open license that prohibits deep fakes - but it is still the main source of issues. It would be a minor edit to simply say "well then not open source" but that would cause problems for adoption: many enterprises can only work with open source. The prescription itself seems to need more grounding in the complexity of software licensing.

Another prescription is watermarking and relying on source code being difficult to edit (involving expertise). However a large subjective issue is raised here. The Article deals in "source code release" and never touches the important part: weight release. The model weights are out in the world, not just the code that generated the models. 

Stable Diffusion, for example, was a release of weights and weights-to-output code, not just source code. Weights being in the wild bypasses the need to edit source code (the expertise claim), since the weights are what a malicious actor would want to get from that source code anyway. Similarly, the watermarking (which gets optionally bolted onto the weights by the source code) is ineffective because the weights are out there in the wild, and weights on their own would need to have had the watermarks embedded via SynthID. And even this safeguard is ineffective because in-weight watermarks can be fine-tuned or purified out once weights are public.  The word "weight" does not come up at all in the article, despite weights being the central object of interest to third party developers. This seems to raise many questions.

## *Prohibiting Generative AI in Any Form of Weapon Control* 
39th Conf. on Neural Info. Processing Sys (2025) [Source](https://neurips.cc/virtual/2025/loc/san-diego/poster/121921)

(NeurIPS is generally understood to be the best AI/ML conference)

> [!note] Article Metadata
> - **Who wrote it?** — GMU Professor (previously UVA Systems Engineering PhD; Duke Professorship)
> - **How objective is the issue?** — Objective
> - **How central is the issue to the article?** — I just read the technical part so I don't know
> - **Outcome if the article is adopted** — No idea

This paper is cited in [[📄A Technical Audit of Law Journals#*Nondeterministic Torts: A Technical Approach to AI Liability*|Nondeterministic Torts: A Technical Approach to AI Liability]]. I say at fn.9 

> Cummings does not substantiate the Note’s key premise, though. Hers is a policy position paper, rather than an empirical paper seeking formal correctness. Read in context, it is not a substantiated claim that—literally interpreted—all connectionist AI models are neural networks, or that all neural networks are non-deterministic, or that no two outputs of the same input are ever the same. Such literal claims would contradict the Note’s other sources and are easily falsified.

Getting into her paper seemed too in the weeds for a student response, but I find my equivocation "not seeking formal correctness" to be incomplete. Her paper uses this sentence as setup
> Also known as neural networks, connectionist AI models are non-deterministic, meaning every time they are run, even with the same input, the outputs will be different

There are two important propositions in this sentence:
1. Connectionist AI models are non-deterministic
2. Every time non-deterministic networks are run, the outputs will be different

They are each incorrect: 
1. [[📄A Technical Audit of Law Journals#*Nondeterministic Torts A Technical Approach to AI Liability*|Nondeterministic Torts]]' Response addresses this in depth
2. Outputs "will" be different means you will never get the same output. The paper should replace "will" with "can"

The paper also includes a graph that involves a spectrum of determinism, which is the same issue from the Harvard JOLT paper: [[📄A Technical Audit of Law Journals#^0f2b53]].

## *Brain Decoders Create a New Federal Evidence Problem*
jurist.org [Source](https://www.jurist.org/commentary/2026/08/brain-decoders-create-a-new-federal-evidence-problem/)

> [!note] Article Metadata
> - **Who wrote it?** — Another UNC Law 1L 
> - **How objective is the issue?** — Not an issue, just what I would find interesting as a follow up

The article:
> Machine-generated text reconstructed from brain activity is now accurate enough to approximate what a person heard, imagined or attempted to say. This is a capability that, offered as criminal evidence, would let prosecutors put words in a defendant’s mouth while bypassing nearly every safeguard the Federal Rules of Evidence builds around human testimony

Two follow-ups to the article would be interesting. I don't know any Evidence rules so I'm gonna take all that at face value. Very cool paper.

On the doctrinal side, since this is essentially a compelled self-incrimination issue, I would be interested to hear about what could make this workable under the Fifth Amendment (and potentially Fourth). From a quick search, *Schmerber* allows for constitutionally sanctioned forced blood draw on the theory that blood is physical rather than testimonial. *United States v. Semrau* says that fMRI lie detection results are inadmissible due to accuracy concerns (under 702, not 5A), and *Doe v. United States* puts compelled disclosure of the contents of one's mind on the protected side of the *Schmerber* line.

On the technical side, the Tang et al. paper cited says

> we tested whether successful decoding requires subject cooperation and found that subject cooperation is required both to train and to apply the decoder.

"let prosecutors put words in a defendant’s mouth" from the Jurist paper seems to assume an uncooperative subject, but Tang says the decoding doesn't work on uncooperative subjects. Is there some concern about defendants who don't know how to properly be uncooperative and defeat the brain scan?

The scan reconstructs stuff that the defendant is thinking about during the scan, so if we were looking to get the location of a weapon out of him/her, he/she would have to be actively thinking about that location for retrieval. 

I think this could also interact well with Andrea Roth, _Machine Testimony_, 126 Yale L.J. 1972 (2017). [Source](https://yalelawjournal.org/article/machine-testimony)

> But the law on machine conveyance is confused: courts shoehorn them into existing rules by treating them as “hearsay,” as “real evidence,” or as “methods” underlying human expert opinions . . . .  explores credibility testing in the form of front-end design, input, and operation protocols; pretrial disclosure and access rules; authentication and reliability rules; impeachment and courtroom testing mechanisms; jury instructions; and corroboration rules
# Disclaimer

I'd like to generally disclaim that although I state things like "X is true," everything should be read with "it seems to me that X is true" or similar "I could definitely be wrong on this" asterisks being there in spirit

I also got one wrong earlier (though the error never hit the live website): *Disability Discrimination by Clinical Algorithm* in N.C. L. Rev. 

"Even when she chose a cutoff threshold at the 99th percentile of the score distribution (and, thus, only evaluated the accuracy of the risk scores of the highest one percent of all patient scores), she found that the algorithm generated false positives eighty-nine percent of the time" wasn't explaining a false positive rate of 89% like I thought, but rather false discovery rate. 

I'm also not keeping the sources and formatting and such on this post standard.

# Results and Recommendations

Because my goal is private practice, legal scholarship will remain a side project rather than a focus. I expect I will disengage with it sooner rather than later, as it is extremely effort-intensive. This audit and its papers were mainly made as a demonstration for a friend. 

Each of these papers is the product of teams of people selected from the most competent at the relevant institution. Yet there seems to be consistent signoff on papers with glaring fundamental flaws. Many are noticeable from reading the abstract. A number involve sources that do not support the paper or establish the opposite of what the paper says they do. 

I recommend that anyone writing a law paper on AI or another technical subject cite the actual research as opposed to marketing materials or pop articles. I also recommend a technical review step on top of standard review.

[^2]: The frontier problem in the field of causal inference concerns the exogenous variables and their bearing on the adequacy and completeness of causal models. If it were possible to rule out, with the help of computer-assisted mathematical analysis, that any variables that remained exogenous to the model influence the endogenous variables in a way that distorts the causal model, including its structural equations, then causal analysis could be formalized and computerized in full. Computers equipped with the necessary software could take over and extrapolate causal relationships from sets of observational data. Once digital machines understand the concept of causation, one can speak of Causal AI. This will mark a major step in the development of digital systems truly deserving the label of artificial intelligence. With an understanding of causation, many errors and hallucinations that are characteristic of the current generation of large language models *will* disappear. 

[^3]: (3) is correct but accuracy (being right) and certainty (being sure of your prediction) are mixed together in the Article's inferential step

[^4]: Patrick Lewis et al., *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*, 33 ADVANCES NEURAL INFO. PROCESSING SYS. 9459, 9460 (2020) (defining $p_{\text{RAG-Sequence}}(y \mid x) \approx \sum_{z \in \text{top-}k(p(\cdot \mid x))} p_{\eta}(z \mid x) \prod_{i}^{N} p_{\theta}(y_{i} \mid x, z, y_{1:i-1})$, in which the retrieved document $z$ enters as a latent variable marginalized over per-token next-token distributions. So, not a substantive change in how LLMs work.)

[^5]: Varun Magesh et al., _Hallucination-Free? Assessing the Reliability of Leading AI Legal Research Tools_, 22 J. EMPIRICAL LEGAL STUD. 216 (2025) (finding Lexis+ AI and Westlaw AI-Assisted Research hallucinate on 17% and 33% of queries respectively, notwithstanding vendor claims that RAG "eliminat[es]" hallucination).

[^7]: Nicholas Carlini et al., *Quantifying Memorization Across Neural Language Models*, 11th Int'l Conf. on Learning Representations (ICLR 2023) (finding that a 6-billion-parameter model memorizes at least 1% of its training corpus in a form extractable verbatim by prefix prompting).

[^8]: Jordan Hoffmann et al., *Training Compute-Optimal Large Language Models*, 36th Conf. on Neural Info. Processing Sys. (NeurIPS 2022) (deriving optimal parameter count as a function of training compute budget, with model size and training-token count scaling in equal proportion).
