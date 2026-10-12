# AI PM Portfolio Context

## Project Purpose

This repository is the starting point for a professional portfolio for an AI Product Manager. The goal is to make it easy for hiring teams, product leaders, founders, and collaborators to understand the author's product judgment through credible, concise evidence of work.

The portfolio should show how the author identifies valuable problems, decides whether AI is appropriate, turns uncertain opportunities into testable products, works across technical and business teams, and measures outcomes responsibly. It should not present AI as a feature by itself or substitute polished visuals for evidence.

## Current State

The repository is not yet a published portfolio website. It currently contains two self-contained browser-game prototypes and their product requirements documents:

- `memory-game.html` and `PRD_dark_theme.md`
- `snake-game.html` and `PRD_snake_game.md`

These projects can demonstrate product scoping, requirements, interaction design, implementation constraints, iteration, and verification. They are not AI products and must not be represented as proof of AI-specific results. Add separate, truthful AI product case studies when the author can provide the underlying work and evidence.

`README.md` is the repository's public-facing orientation and setup guide. This file is the internal working brief that future contributors or AI assistants should read before changing the portfolio direction or content.

## Intended Audience and Visitor Need

Primary visitors are recruiters and hiring managers screening for AI Product Manager roles. Secondary visitors include product and engineering peers, founders, and potential collaborators.

Visitors should be able to answer these questions quickly:

- What product problems can this person lead?
- How do they distinguish a valuable AI use case from a conventional software problem?
- How do they handle data, model quality, uncertainty, human review, privacy, and failure modes?
- What did they personally own, what changed because of their work, and what evidence supports that claim?
- How can they contact or learn more about the author?

## Positioning and Editorial Principles

- Lead with the author's real role, domain strengths, and specific product value. Do not invent a title, years of experience, employers, outcomes, credentials, or customer access.
- Prefer first-hand artifacts, measurable results, and clearly attributed decisions over generic claims such as "AI enthusiast" or "visionary leader."
- Separate shipped outcomes from prototypes, estimates, hypotheses, and retrospective recommendations.
- State the author's contribution and collaborators' contributions accurately.
- Anonymize confidential work and remove customer-identifying, proprietary, or sensitive data unless explicit permission exists to share it.
- Explain AI choices in terms of user and business value, including when a non-AI approach would be better.
- Discuss meaningful risks and trade-offs, not only successful paths.
- Keep writing clear, specific, and scannable. Define technical terms when a non-specialist hiring reader may not know them.

## Recommended Portfolio Structure

The initial portfolio should be small and focused. Add pages only when they improve understanding or evidence.

1. **Home**: Name, target role, concise positioning statement, selected case studies, and contact link.
2. **Case studies**: Two or three strong, evidence-backed examples are preferable to a long list of shallow summaries.
3. **About**: Relevant experience, domains, working approach, and a downloadable resume if the author chooses to publish one.
4. **Contact**: A professional email or an explicitly chosen public profile link.

Avoid adding testimonials, personal details, social links, or downloadable files until the author provides and approves them.

## Case Study Standard

Each case study should make the reasoning and evidence easy to follow. Use only sections that fit the project, and identify unavailable or confidential information instead of guessing.

1. **Snapshot**: Project, date, status, team, author's role, and disclosure level.
2. **Problem and users**: Who experienced the problem, how often it occurred, and what evidence established its importance.
3. **Opportunity assessment**: Desired user and business outcomes; why AI was or was not appropriate; relevant baseline or simpler alternatives.
4. **Discovery and validation**: Research methods, participants or data sources, assumptions tested, and confidence limits.
5. **Product decisions**: Target workflow, MVP boundary, prioritization, and important trade-offs.
6. **AI and system design**: Model or service choice where shareable, data inputs, evaluation approach, latency or cost constraints, integrations, and human oversight.
7. **Responsible AI and failure handling**: Privacy, security, fairness, reliability, transparency, escalation, and fallback behavior relevant to the product.
8. **Measurement**: User and business success metrics, quality metrics, guardrails, and how they were evaluated.
9. **Delivery and adoption**: Collaboration, rollout, operations, feedback loops, and iteration.
10. **Results and learning**: Verified outcomes with timeframe and context, limitations, lessons, and next steps. Label estimates and prototype results explicitly.

## AI Product Competencies to Evidence

Use case studies to demonstrate relevant skills through actual decisions and outcomes rather than a keyword list:

- User problem discovery and opportunity sizing
- AI suitability assessment and baseline comparisons
- Product strategy, MVP definition, and prioritization
- Data readiness, model evaluation, and quality trade-offs
- Human-in-the-loop workflows and user trust
- Responsible AI, privacy, security, and risk management
- Cross-functional execution with design, engineering, research, legal, and operations
- Experimentation, launch planning, adoption, and measurable business impact

The author should choose which competencies match their real experience. Do not imply mastery of areas that are not supported by evidence.

## Design and Technical Direction

- Build for quick scanning by busy hiring readers: clear hierarchy, concise project summaries, and direct access to detailed work.
- Use responsive layouts, semantic HTML, keyboard-accessible navigation, visible focus states, readable contrast, and reduced-motion preferences.
- Prioritize fast loading, stable links, useful page titles and descriptions, and good mobile behavior.
- Do not add decorative animation or AI-generated imagery that makes the work harder to understand.
- Keep project artifacts easy to inspect and link to from the portfolio.
- Current repository examples are plain HTML/CSS/JavaScript with no package manager, framework, backend, or build pipeline. A static portfolio is a sensible initial direction, but choose a framework only if a concrete requirement justifies its maintenance cost.
- Do not introduce hosting, analytics, forms, third-party scripts, or external services without an explicit privacy and maintenance decision.

## Personalization Inputs Still Needed

The portfolio must remain a scaffold until the author supplies and approves these details:

- Preferred name, professional title, location or time zone if desired, and contact method
- Target role types, industries, and geographic or remote-work preferences
- Work history, responsibilities, and collaborators for each shareable case study
- Two or three projects with problem evidence, decisions, artifacts, outcomes, and lessons
- Which details are confidential and how each case study may be disclosed
- Resume, professional profiles, and any approved references or testimonials
- Preferred visual direction and whether the current game prototypes belong in a public portfolio

Keep placeholders visible in draft content so missing information is not mistaken for fact. Do not publish placeholder text as finished portfolio copy.

## Suggested Setup Sequence

1. Inventory the author's experience and collect evidence before choosing a site template.
2. Select two or three case studies and complete the case-study outline for each.
3. Review every claim for accuracy, attribution, confidentiality, and evidence quality.
4. Decide the initial information architecture and a visual system that supports scanning and accessibility.
5. Build the smallest responsive static site that presents the approved content clearly.
6. Test navigation, mobile layout, accessibility basics, links, performance, and contact paths.
7. Publish only after replacing placeholders, reviewing disclosures, and confirming all public links.

## Definition of Ready to Publish

- The author's identity and positioning are approved and factual.
- At least one complete case study clearly states the problem, the author's role, key decisions, and substantiated outcome or explicitly labeled learning.
- Confidentiality and attribution have been reviewed.
- No placeholder claims remain in public pages.
- Navigation, responsive behavior, accessibility basics, and contact links have been checked.
- The README accurately explains how to preview and maintain the portfolio.