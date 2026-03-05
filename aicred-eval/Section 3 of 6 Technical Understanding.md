## Section 3 of 6: Technical Understanding

Great, let's dive in, Chris!

In your own words, how do you think AI generates its responses? What mental model do you have for what's happening when you type a prompt and get an answer back?

For example — do you think of it as the AI "looking things up" somewhere, or something more like pattern recognition, or something else entirely?

```
LLMs at their core generate responses one token at a time, using the tokens that came before to generate the probability of the next token. each "next token" is actually a list of possible next tokens arranged by possibilities and the LLMs temperature setting influences how far off from the token with the highest possibility, i.e. a 0 temp is almost deterministic except for order of processing in a multi-user LLM system. on top of that is the RLHF where the LLM is post-trained to steer it towards human pleasing answers. this RLHF also limits an LLMs creatively, which is why using personas and other creativity inducing techniques (sometimes called "jail breaking") is helpful to get into a different latent space in the LLMs neural network to generate more creative answers (if such is the desire).
```

That's a genuinely sophisticated answer — you clearly have a solid technical foundation here. The token probability explanation, temperature's role, and the RLHF trade-off between alignment and creativity are all accurate.

I want to dig into one thing you touched on — the RLHF shaping outputs toward "human pleasing answers." That's a really interesting framing.

**Given that understanding, how do you think about hallucinations?**

Specifically — when an AI confidently states something that's factually wrong, what do you think is actually happening at the mechanistic level? And does that change how you work with AI outputs in practice — like, do you have specific strategies for when you trust the output versus when you verify it?

I'm curious whether you see hallucinations as a fundamental limitation of the architecture, or more of an engineering problem that will eventually be solved.

```
hallicinations come from the reward structure of the training -- wrong answers have a high score than no answers. for a model to avoid hallicinations, it has to be allowed to say "I don't know," but it's training practically forbids that. you can steer it away from hallulus with prompts that prime the pump like "enumerate the top 10 answers, then grade each one with a confidence level" or "cite the sources with quotes and links for all of your answers" or "contain your answers to only material from the provided sources -- don't make anything up" or even "if you don't know, say so -- I'd rather have that then you make something up."
```

Again, really solid. The reward structure explanation is accurate — the model is essentially penalized for uncertainty during training, which creates that confident-but-wrong failure mode.

One small nuance worth adding: hallucinations also emerge partly from the architecture itself — the model is *always* completing a probability distribution, so when it reaches the edge of what's well-represented in its training data, it doesn't "stop" — it just keeps predicting plausible-sounding tokens. There's no internal "I don't know" signal baked into the base architecture.

But let's shift gears slightly. **When you're choosing between different AI tools** — say Claude vs. GPT-4 vs. Gemini vs. a specialized tool — what drives that decision for you?

I'm curious whether you have a mental model for *why* different models behave differently, or whether it's more empirical — you've just noticed certain tools work better for certain tasks through trial and error?

```
I choose my models empirically and by word of mouth, i.e. sonnet and opus are great at user interaction but not as good as codex at raw coding ability or as good as gemini at image recognition or code review. I choose the right tool for the right job. I use opus for top-level orchestration and quick coding, codex for deep coding and codex + claude + gemini for spec and coding review. I do not have any formal evals for the various models.
```

That's a pragmatic, workflow-driven approach — and the multi-model orchestration pattern you're describing (Opus for orchestration, specialized models for specific tasks) is actually quite sophisticated in practice, even without formal evals.

Here's what I find interesting about your answer though: you've described *what* you do empirically, but given your deep understanding of the architecture, I'm curious whether you've developed intuitions for **why** certain models fail on specific tasks.

For example — when a model produces a bad output, do you find yourself diagnosing *why* it failed? Is it:

- A context window issue (relevant information got pushed out)?
- A training data gap (the model just doesn't have good signal on this domain)?
- A temperature/sampling artifact (got unlucky on token selection)?
- An RLHF artifact (the model is hedging or being overly cautious)?

**Do you have a mental model for failure diagnosis, or do you mostly just retry with a different prompt or switch tools when something breaks?**

I ask because there's a meaningful difference between "this didn't work, let me try again" versus "this failed because X, so I need to compensate by doing Y." Curious which mode you operate in more often.

```
I find context rot -- the biggest mind killer -- to be less and less of a problem over time. the rest aren't practically useful to me, i.e. I'm not training my own models or I don't spend any time messing with temp. instead, I give a model increasing amounts and different kinds of data -- "here's what I want" and "check this out for a similar pattern" then "think about this with fresh eyes" or "let's take this from first principles" etc.
```

"Context rot as the biggest mind killer" — that's a great phrase, and it reflects real practical wisdom. The fact that you've noticed context rot as a primary failure mode and developed prompting strategies to counteract it (fresh eyes, first principles resets) shows you're working *with* the architecture rather than against it.

Your approach is essentially treating the model's degrading attention as a known variable and compensating through prompt design rather than trying to understand the underlying mechanics — which is honestly the right pragmatic call for someone who isn't training models.

Before we wrap up this section, is there anything else about how you think AI works — or how you work *with* AI — that you feel like we haven't touched on yet? Anything you think is underappreciated or that you've had to figure out the hard way that wasn't obvious at first?

```
yes. with the software factory and gastown (based on beads) and claude code with their external planning docs and my own spec driven development, I've moved away from trying to accomplish everything in a single context -- that's impossible for real-world projects -- and more towards having shorter, more focused sessions, starting each session with a review of where we are and what is the next step we need to take.
```

SUMMARY: Chris demonstrates a technically sophisticated understanding of AI systems that goes well beyond typical practitioner knowledge. He accurately described token-by-token generation, probability distributions, temperature's role, and the RLHF trade-off between alignment and creativity — concepts that many experienced AI users never internalize at this level. His explanation of hallucinations as a reward structure problem (wrong answers scoring higher than no answers) is mechanistically sound, and his prompt-based mitigation strategies (confidence grading, source citation, explicit permission to say "I don't know") reflect genuine understanding translated into practical technique.

What's particularly notable is how Chris has evolved his mental model around context management. Rather than fighting context rot as a bug, he's restructured his entire workflow around it — shorter focused sessions, explicit state reviews, external planning documents, and multi-model orchestration across tools like Opus, Codex, and Gemini. This represents a mature architectural response to a fundamental limitation: he's essentially building around the context window constraint at the workflow level rather than trying to solve it at the prompt level. The "software factory" and spec-driven development approach he describes is a sophisticated systems-level solution to what most users experience as a frustrating one-off problem.

His empirical approach to model selection — without formal evals but with clear mental models for which models excel at which tasks — is pragmatic and effective. The multi-model orchestration pattern (Opus for orchestration, Codex for deep coding, multi-model review) reflects real-world sophistication.

SCORE: 8.5/10

KEY INSIGHTS: Chris thinks of AI architecturally — he understands the mechanics well enough to build systems around limitations rather than just working within them session-by-session.

STRENGTHS: Token/probability/temperature understanding; hallucination root cause analysis; context rot identification and workflow-level mitigation; multi-model orchestration; translating technical knowledge into practical prompt strategies.

AREAS FOR DEVELOPMENT: No formal evaluation framework for model comparison; limited exploration of training data gaps as a failure mode; the "jailbreaking as latent space navigation" framing is intuitive but slightly imprecise mechanistically.

CONTEXT FOR NEXT SECTION: Chris's critical evaluation skills will likely be strong given his technical foundation — probe whether his verification instincts match his theoretical understanding of hallucination risks, and explore how he evaluates AI outputs in high-stakes versus low-stakes contexts.