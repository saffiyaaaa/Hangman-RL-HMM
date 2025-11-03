🧠 Hangman RL-HMM Hybrid Model
📘 Overview

This project combines Reinforcement Learning (RL) and a Hidden Markov Model (HMM) to play a Hangman-style word prediction game.
The HMM models the statistical patterns of language, while the RL agent learns optimal guessing strategies through interaction and feedback.

🎯 Objectives

Model sequential letter dependencies using a probabilistic HMM.
Train an RL agent (Q-learning) to improve letter prediction through trial and reward.
Demonstrate how combining probabilistic reasoning and reinforcement learning enhances decision-making in language-based tasks.

🧩 Model Design
🔹 Hidden Markov Model (HMM)

Hidden States: Represent possible underlying letters or phonetic states.
Observations: Visible letters in the word being guessed.
Transition Probabilities: Likelihood of moving from one state (letter) to another (e.g., ‘t’ → ‘h’).
Emission Probabilities: Probability of a state emitting an observed letter.
Learned using frequency-based estimation from the training corpus (similar to N-gram modeling).

🔹 Reinforcement Learning Agent

Goal: Guess the missing letters in a word correctly.
Algorithm: Deep Q-Learning (DQN).
Reward:
+1 for a correct guess.
−1 for a wrong guess.
+5 for completing a word.
Action Space: 26 English alphabet letters.
Learns to maximize long-term reward through iterative gameplay and feedback.

⚙️ Training Pipeline

Corpus Preparation: Load and preprocess corpus.txt.
HMM Training: Estimate transition and emission probabilities.
RL Interaction:
The agent observes the current masked word state.
Selects a letter (action).
Receives feedback (reward) and updates Q-values.
Convergence: The model improves over multiple episodes (e.g., 2000).

💡 Key Insights

The HMM captures language regularities, narrowing the search space.
The RL agent learns adaptive guessing, improving efficiency.
The hybrid system blends statistical modeling (HMM) with dynamic learning (RL), outperforming purely random guessing.

🚀 How to Run (Google Colab)

Upload your corpus.txt file to Colab.
Upload the notebook or script file (e.g., hangman_rl_hmm.py or .ipynb).
Run the following to start training:

agent, hmm = train_pipeline("corpus.txt", episodes=2000)

Evaluate the trained agent:
avg_reward, success_rate, rewards = evaluate_agent(agent, hmm, episodes=200)

The notebook will display training progress and final results (average reward, success rate).


