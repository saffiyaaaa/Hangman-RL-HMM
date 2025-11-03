Hangman RL-HMM Hybrid Model

Overview

This project combines Reinforcement Learning (RL) and a Hidden Markov Model (HMM) to play a Hangman-style word prediction game.
The HMM models language patterns, while the RL agent learns to guess letters strategically based on feedback.

Objectives

Use an HMM to learn transition (between letters) and emission (letter likelihood) probabilities from text data.

Train a Q-learning agent to maximize rewards by correctly predicting letters and completing words efficiently.

Demonstrate how probabilistic models and reinforcement learning can work together for sequential prediction tasks.

Model Design
Hidden Markov Model (HMM)

Hidden States: Represent possible underlying letters or phonetic patterns.

Observations: Actual visible letters in words.

Transition Probabilities: Estimate the likelihood of moving from one letter/state to another (e.g., ‘t’ → ‘h’).

Emission Probabilities: Estimate the chance of a hidden state producing a visible letter.

These probabilities are learned directly from the training corpus using frequency counts (similar to N-gram modeling).

Reinforcement Learning Agent

Goal: Guess missing letters in the Hangman game.

Algorithm: Deep Q-Learning (DQN).

Reward: Positive for correct guesses, negative for incorrect ones.

Action Space: All possible alphabet letters.

The agent updates its Q-values to maximize expected reward based on state transitions and outcomes.

Training Process

Load and preprocess the text corpus.

Train the HMM to compute transition and emission probabilities.

The RL agent interacts with the environment (Hangman game) for several episodes:

Observes the current word state.

Selects a letter based on its policy (exploration vs exploitation).

Receives feedback and updates Q-values.

Key Insights

The HMM captures language structure, guiding the RL agent toward likely letters.

The RL agent refines guessing strategy over time, balancing exploration and exploitation.

Integration of probabilistic modeling and learning-based decision-making improves overall prediction efficiency.

How to Run (Google Colab)

Upload your corpus.txt file to the Colab environment.

Upload the project script (e.g., hangman_rl_hmm.py or notebook).

Run all cells.

agent, hmm = train_pipeline("corpus.txt", episodes=2000)


To evaluate performance:

avg_reward, success_rate, rewards = evaluate_agent(agent, hmm, episodes=200)


Results (accuracy, reward trends) will appear in the output.