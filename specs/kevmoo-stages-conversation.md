# Chris Sells & Kevin Moore: Stages of Growing as an Agentic Coding Engineer

*Extracted from Google Chat DM, January 25 – March 1, 2026*

---

## Context

Kevin Moore (kevmoo) is a senior Dart/Flutter engineer at Google, maintainer of `json_serializable` and other key packages. Chris Sells has been deep into agentic coding and has been (somewhat gleefully) guiding Kevin through the stages of becoming an AI-native developer.

---

## The Conversation

### Stage 1: Curiosity & First Contact (Jan 25, 2026)

**Kevin:** "reading an internal deck about how to code w/ agents – I wish I could share....SUPER interesting"

Chris responds by sharing a PR he built with Gemini 3 Pro Preview — one of 6 projects he was working on that day.

**Chris:** "this is one of 6 projects I was working on today. if you aren't already doing agentic coding, you should be."

**Kevin:** "I'm a baby. you're inspiring me!"

Chris walks Kevin through the workflow: integrating Gemini suggestions, addressing code review feedback via the agent, tackling CI failures. Kevin is watching in real-time as Chris uses agents to iterate on a PR against Kevin's own repo.

### Stage 1.5: Learning to Fish (Jan 30, 2026)

Kevin asks Chris to point his "magic robot" at a bug someone filed. Chris refuses — lovingly:

**Chris:** "I'm going to say 'no' to that with love and for your own good. Instead, I'm going to teach a man to fish. Load your json_serializable project into Antigravity and paste the link to the bug into your Gemini 3 Pro Preview chat in Planning mode and press Enter. Read the plan and give feedback on it until you're happy and then let Gemini fix the bug for you."

**Kevin:** "okay...it's running..."

Later: "Oh yeah! It did. Mostly. Needed to nudge a bit, but it did most of the work. thanks!"

### Stage 2: The Exoskeleton / "Developer Diarrhea" (Feb 5, 2026)

Kevin has been coding with agents for ~10 days and is hooked:

**Kevin:** "Dude. It's like – I feel like I'm wearing an exoskeleton. So changes that would be a hassle to deal with...or to debug.... I'm like...well...let's jump in and TRY. So I code SO MUCH MORE and get so much more done! ...so much done in the last 3 days. it's ADDICTING!"

**Chris:** "ha. you've arrived at the next well-known stage where you ONLY want to code so you can turn every idea you've ever had and every new idea you have along the way into working, solid code. we call this unblocking 'developer diarrhea.' remember to hydrate. : )"

**Chris:** "there are more stages to come..."

**Chris:** "welcome to AI native development. I'm happy to be your guide."

### Stage 3-4 Check-in: Multi-Agent, Self-Improving Systems (Mar 1, 2026)

Kevin shares his `personal_dotfiles` repo showing multiple agents communicating with each other, including a file called `notes_for_the_other_agent.md`.

**Kevin:** "JFC dude, so what stage am I in now?"

**Chris:** "Multiple agents talking to each other? Solving long standing problems? Up at all hours? Those are elements of stage 3 and 4 for sure. How many projects are you working on at once? How do you manage them? How much code do you write? Review? Read? I like the use of 'we' in your story : )"

Chris probes deeper with diagnostic questions:

- **On agent memory:** "Do you have one or more agents with memory about your various projects? How did you build that agent? Does it write code, drive an instance of an agent that writes code or orchestrate a swarm to write the code?"
  - Kevin: "I am not there yet"

- **On relationship with code:** "What about your relationship with code? Still writing it? Reading it? Having standards for best practices?"
  - Kevin: "I'm still reading it and having standards for good practices"

- **On best practices:** "So you're reading the code and manually applying the best practices? Have you considered creating a doc with those best practices and asking the agent to apply them for you? Have you considered having a swarm of agents from different vendors review your code and then use an agent to consolidate those reviews to apply best practices?"

- **On language choice:** "Are you still reading/writing dart? Have you considered using another language with heavy type safety guard rails for the agents that you're less personally invested in from a code beauty pov?"

Kevin reveals he does have skills that agents update:

**Kevin:** "Oh yeah I have many skills. And I have the agent update the skills as it's reviewing the code"

**Chris:** "Aha! You're self improving your system as you go! Are you manually asking the agent to update its skills or does it happen automatically? Are you syncing them across agents? Across machines?"

**Kevin:** "I don't have a lot of machines. I just went from 1 to 2. slow down, yoda"

### Chris's Current Setup (Stage 5+?)

Chris describes his own advanced setup for contrast:

**Chris:** "I'm on two right now but I just moved one of them to be the central server. It's a VPS in the cloud that now my laptop or my phone or my tablet or any web UI on the planet is mostly just a surface for the multiple agents across multiple projects that I've got running on my single centralized server. Now I don't have to worry about closing my laptop and killing all my agents. The laptop is just a UI surface"

**Chris:** "I also just moved to a set of sync tabs on Opera so that when I move between my phone and my laptop I have all of the same projects and all of the same tabs synced between the two machines and it's also easy to alt tab right? Chrome is for other stuff. Opera now provides the tabs for my agent sessions"

**Chris:** "And instead of having a terminal session into that VPS, which you know sucks when it comes to using it from your phone. I use a combination of a web hosted file browser finder replacement on the VPS that I can get to from my phone or my laptop. And I also use one dedicated cloud code session in my home folder to do global things across the entire machine"

---

## Implied Stage Framework (Extracted)

| Stage | Name | Key Characteristics |
|-------|------|-------------------|
| 1 | **Curiosity / First Contact** | Reading about agents, watching others use them, first experiments |
| 2 | **The Exoskeleton / Developer Diarrhea** | Addicted to coding with agents, massive productivity boost, turning every idea into code, can't stop |
| 3 | **Multi-Agent Communication** | Agents talking to each other, notes between agents, solving problems across sessions |
| 4 | **Self-Improving Systems** | Agents updating their own skills/config, automated best practices, review swarms |
| 5+ | **Infrastructure as UI Surface** | Centralized cloud agents, devices as thin clients, cross-machine sync, phone-first agent management |

### Diagnostic Questions Chris Uses to Assess Stage

1. How many projects are you working on at once?
2. How do you manage them?
3. How much code do you write vs. review vs. read?
4. Do you have agents with memory about your projects?
5. Does the agent write code directly, drive other agents, or orchestrate a swarm?
6. Are you manually applying best practices or has the agent internalized them?
7. Are agents self-improving their own skills?
8. Are skills synced across agents? Across machines?
9. What's your relationship with the code itself? Still attached to code beauty?
10. Is your laptop a development machine or just a UI surface?
