Hi, I'm Ben, a 1L at UNC Law. I'm looking to apply my subject matter expertise (AI research at MIT) to law. In reading through contemporary legal scholarship, I've found that the technical details of AI are often misunderstood. Occasionally inferences are drawn from those misunderstandings that cascade into disastrous policy recommendations. 

Most notably this cascade has yielded 
- the largest removal of First Amendment protections ever advanced (Stanford)
- a tort liability regime that would allow LLM developers like OpenAI and Anthropic thwart strict liability in its entirety via a simple software update ([[A Technical Audit of Law Journals#*Nondeterministic Torts A Technical Approach to AI Liability*, 135 Yale L.J. 2719 (2026)|Nondeterministic Torts: A Technical Approach to AI Liability, 135 Yale L.J.]])

These findings prompted me to create this document, meant to be readable for a general audience. I am actively writing papers on the major issues and will, if I remember, put all issues I identify on this list. 

I'd like to generally disclaim that I'm going to state things without the standard "but I may be wrong" equivocations but, in general, you can assume I meant it to be there in spirit.

# Yale

## *Nondeterministic Torts: A Technical Approach to AI Liability*, 135 Yale L.J. 2719 (2026)
[Source](https://yalelawjournal.org/note/nondeterministic-torts-a-technical-approach-to-ai-liability)

Who wrote it? - Yale Student Note
How objective is the issue? - Objective
How central is the issue to the article? - Central. The title itself is a reference to the technical issue
What's the outcome if the article is adopted - A tort regime for LLMs that tech firms can thwart with near-zero cost

I'm very proud of this paper, which involved an original mathematical proof that refutes the exact core premise of the Yale Note, as well as the introduction of Lipschitz continuity as a concept into legal scholarship (I had a friend at LexusNexus do a thorough check). 

L-continuity is the essential formal property that makes a product verifiably safe (or, currently, unsafe) at AI scale, and I expect it will be hard for law to handle the pacing problem (tech evolving faster than doctrine can regulate) in torts without reliance on it.

SSRN paste here

# Harvard

## *Traditional and Computational Canons*, 39 HARV. J.L. & TECH. 287 (2025)
[Source](https://jolt.law.harvard.edu/assets/articlePDFs/v39.1/Traditional-and-Computational-Canons.pdf)

Who wrote it? - UChicago Law Instructor (previously MIT PhD in Cognitive Sci)
How objective is the issue? - Objective
How central is the issue to the article? - Not at all. It's also a cool paper. I mention this mainly to characterize [[A Technical Audit of Law Journals#*Nondeterministic Torts A Technical Approach to AI Liability*, 135 Yale L.J. 2719 (2026)|Nondeterministic Torts A Technical Approach to AI Liability, 135 Yale L.J. 2719 (2026)]]
What's the outcome if the article is adopted - The issue doesn't affect doctrinal recommendations

> Lower temperatures (e.g., 0) make outputs more deterministic, while higher temperatures (e.g., 1–2) make them more varied.

> A systematic sweep across nine values, ranging from fully deterministic (0) to maximally stochastic (2)

The paper characterizes temperature as a spectrum from "more" deterministic to more stochastic. 

1. The axis is wrong. Stochasticity (variedness/randomness) is not the opposite of determinism: nondeterminism is. 
2. Something cannot be "more deterministic." Determinism is not a spectrum: it is a property of processes for which supplying the same inputs always produces the same outputs.[^1] 
3. High temperatures do not induce nondeterminism. This is a more complex explanation that I address in my reply to [[A Technical Audit of Law Journals#*Nondeterministic Torts A Technical Approach to AI Liability*, 135 Yale L.J. 2719 (2026)|Nondeterministic Torts A Technical Approach to AI Liability*, 135 Yale L.J. 2719 (2026)]]

[^1]: *Non-Determinism and the Lawlessness of Machine Learning Code*, 2022 SYMP. ON COMPUT. SCI. & L. 1, 2-3. Cooper, Frankle, and De Sa (by logically inverting their definition of nondeterminism). [src](https://afedercooper.info/paper/cooper2022lawless.pdf)
# Stanford

## *Speech Certainty: Algorithmic Speech and the Limits of the First Amendment*, Sta. L. Rev. 77 (2025)
**[Source](https://review.law.stanford.edu/wp-content/uploads/sites/3/2025/01/Austin-Levy-77-Stan.-L.-Rev.-1.pdf)**

Who wrote it? - Two practitioners, both Stanford Law alums
How objective is the issue? - Subjective, but sometimes objective
How central is the issue to the article? - It is the core of the article
What's the outcome if the article is adopted - First Amendment protections are removed from the outputs of systems involving gradient descent, which is a much more sweeping ban than a targeted removal of protections for social media content moderation algorithms

> three fundamental characteristics of machine learning: (1) machine learning algorithms write their own rules; (2) machine learning programmers cannot explain those rules; and (3) the algorithms’ predictions are guaranteed to be wrong at least some of the time. Together, as we explore in Part IV, these characteristics prove decisive in the First Amendment analysis

However none of these things are correct in any meaningful way. This was a hard one to address objectively because it is a technical claim using highly underspecified language. 

What is a rule? What does it mean for an algorithm to "write its own" rules when it itself is written by a programmer? What does "explain" mean? To whom? Using what resources? What level of explanation (e.g., "well it's because the numbers get multiplied together and they choose this word") is valid? None of these questions are fully addressed, and a number of citations (Pedro Domingos, Cade Metz) are, in the construction of these "fundamental characteristics," objectively used as substantiation for assertions they don't support.

SSRN paste here
# UChicago

## *Causal AI—A VISOR for the Law of Torts*, U. Chi. L. Rev. Online (2024)
[Source](https://lawreview.uchicago.edu/online-archive/causal-ai-visor-law-torts) 

Who wrote it? - Humboldt University Law Professor
How objective is the issue? - Subjective
How central is the issue to the article? - Central. The title itself is a reference to the technical issue
What's the outcome if the article is adopted - There is no doctrinal recommendation as this is an article that simply predicts future outcomes. Low risk

> Causal AI is within reach.

The main issue is the quote 
> The frontier problem in the field of causal inference concerns the \[external\] variables . . . . If it were possible to rule out . . . that any variables that remained \[outside\] the model influence the \[internal\] variables in a way that distorts the . . . model . . . then causal analysis could be formalized and computerized in full." [^2]

To completely rule out external interference, you would first have to list every single variable in the universe and prove it has zero impact. Because you cannot enumerate an infinite number of background factors, a causal model can never be perfectly sealed from the outside world. It is hard to envision this as a frontier problem - consensus seems to be that causal completeness is not mathematically decidable from data alone.

A second issue is that this "If X then Y" statement then being used as a lead-in for saying "This ***will*** mark a major step in the development of digital systems" and as the justification for the abstract's opener, "Causal AI is within reach." This is an unwarranted inductive leap from a hypothetical to a certainty.

Finally, exogenous variables (what I simplified to "external" variables) are misidentified, which may be the core of this paragraph. The paper says

> exogenous variables, these \[undefined\]\[ \]variables are excluded[^3] from causal models and treated as given.

However what the reasoning in the paragraph relies on is *omitted/unmodeled* variables, not the variables the model already knows about and has chosen to set aside from causality and treat as given. It is much harder to rule out that all the infinite variables in the world don't impact your model than make that same judgement about the ones you already have in hand. Swapping them is what leads to this paragraph's seismic claim.

# UNC

## *Disability Discrimination by Clinical Algorithm*, N.C. L. Rev. 103 (2025)
**[Source](https://scholarship.law.unc.edu/nclr/vol103/iss1/5/)**

Who wrote it? - UW Law Professor, Indiana Law Professor
How objective is the issue? - Objective
How central is the issue to the article? - Hard to tell. It does undercut a very emphasized claim but there seems to be additional parallel evidence (interviews etc.) that make the same point
What's the outcome if the article is adopted - Low risk due to low centrality

> (n.128) the algorithm generated false positives eighty-nine percent of the time

This and and the claims around it swap the roles of precision, accuracy, and false positive rate. For example "accuracy of the algorithm eroded from 11%" seems to then use the same 89% "false positive" number as accuracy (since 100% - 89% = 11%). 

Far from being an 89% false positive rate, the source cited for this footnote says the rate is <1%. 

## *Deepfake Liability*, N.C. L. Rev. 104 (2026)
[Source](https://scholarship.law.unc.edu/cgi/viewcontent.cgi?article=7066&context=nclr)

Who wrote it? - Postdoc at the Hebrew University of Jerusalem, WashU Law Professor (Visiting), Penn Carey Law Professor
How objective is the issue? - Objective, large subjective
How central is the issue to the article? - The subjective is central
What's the outcome if the article is adopted - Only slight effectiveness 

The Article suggests, as one of three prescriptions
> requiring companies to only release their code under an open-source license prohibiting the removal of basic safeguards

However this suggestion goes against the [definition of open-source](https://opensource.org/osd) which says "The license must allow modifications and derived works" and "The license must not restrict anyone from making use of the program in a specific field of endeavor." A similar attempt a similarly "ethical license" has already been made and shut down. Stable Diffusion, the main model that causes these issues, is already released under a non-open license that prohibits deep fakes - but it is the main source of issues. It would be a minor edit to simply say "well then not open source" but that would cause problems for adoption: many enterprises can only work with open source. The prescription itself seems to need more stability in dealing with the license economy.

Another prescription is watermarking and relying on source code being difficult to edit (involving expertise). However a large subjective issue is raised here. The Article deals in "source code release" and never touches the important part: weight release. The models are out in the world, not just the code that generated/helps the models. 

Stable Diffusion, for example, was a release of weights and weights-to-output code, not just source code. Weights being in the wild bypasses the need to edit source code (the expertise claim), since the weights are what a malicious actor would want to get from that source code anyway. Similarly, the watermarking (which gets optionally bolted onto the weights by the source code) is ineffective because the weights are out there in the wild, and weights can't have watermarks bolted on.  The word "weight" does not come up at all in the article, despite weights being the central object of interest to third party developers.



[^2]: The frontier problem in the field of causal inference concerns the exogenous variables and their bearing on the adequacy and completeness of causal models. If it were possible to rule out, with the help of computer-assisted mathematical analysis, that any variables that remained exogenous to the model influence the endogenous variables in a way that distorts the causal model, including its structural equations, then causal analysis could be formalized and computerized in full. Computers equipped with the necessary software could take over and extrapolate causal relationships from sets of observational data. Once digital machines understand the concept of causation, one can speak of Causal AI. This will mark a major step in the development of digital systems truly deserving the label of artificial intelligence. With an understanding of causation, many errors and hallucinations that are characteristic of the current generation of large language models *will* disappear. 

[^3]: Structural causal **models** actually *include* exogenous variables, but the modeled **system** *excludes* them. That is, the whole description of the world sees that they are there, but they aren't part of the core causal relationship described. But this is too nitpick-y
