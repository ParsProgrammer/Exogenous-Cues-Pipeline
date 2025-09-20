# Exogenous-Cues-Pipeline
This is the pipeline where we examined candidate cues.

📖 # Introduction

Many experts argue that democracy is facing a crisis in the 21st century. A major factor is the transformation of the public sphere — the space where political discussion happens.

Social media has a dual role in this process:

Positive: platforms like Twitter/X and Facebook make political debate more open and accessible.

Negative: they fragment discussion, create echo chambers, weaken norms of civil debate, and reduce trust in institutions.

This project investigates these challenges from three perspectives:

Collecting stronger evidence about how social media affects political debate and society.

Understanding the mechanisms behind these effects.

Developing tools to help platforms better support democracy — by improving debate, building legitimacy, and strengthening democratic citizenship.

🧩 The Problem

Most content people see on social media is filtered by engagement-driven algorithms, typically using collaborative filtering.

⚠️ The problem:

These systems maximize clicks, likes, and shares — not information quality.

Misinformation, gossip, and sensationalism often spread as effectively as fact-based journalism.

Directly filtering content for quality is difficult at scale, computationally expensive, and raises censorship/bias concerns.

✅ The alternative: Exogenous cues — signals that indicate reliability based on context rather than content.

Example: partisan diversity of a site’s readership. A more politically diverse audience often correlates with higher information quality.

🎯 Project Goals

Our research is organized into two main phases:

Phase 1 — Identifying Useful Exogenous Cues

We tested several cues against NewsGuard scores (our benchmark for information quality).
NewsGuard rates news domains (0 = unreliable, 100 = highly reliable) using transparent, apolitical journalistic standards.

Explored cues included:

Political diversity of a domain’s broadcasters

Popularity of domains

Skewness of broadcasters’ distribution

Skewness of article distribution

Cognitive centrality of domains (multiple variants)

Cues significantly correlated with NewsGuard scores were retained as predictors.

Phase 2 — Building an Augmented Recommender System

We integrated promising cues into standard recommendation algorithms.
The aim: improve recommendation quality without analyzing or censoring content directly.

Datasets:

Twitter/X data from the US and Germany.

Users’ partisanship was pre-computed, allowing analysis of how domains spread across the political spectrum.

📊 Modeling & Results

We framed the problem as a regression task: predicting NewsGuard scores from contextual cues.

Models applied:

Random Forest → captured non-linear relationships and handled noisy signals.

Elastic Net → more interpretable, highlighted the most relevant features while reducing redundancy.

Key takeaway:

Random Forest ensured robust predictions.

Elastic Net revealed which contextual cues consistently drove information quality.

Together, these approaches balanced accuracy and interpretability.
