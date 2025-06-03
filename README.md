# ETHBelgrade - ImpactScore

**ImpactScore** is an AI-powered, blockchain-backed system that analyzes the potential societal impact of social media content—starting with tweets—and assigns trust scores to users. The platform rewards responsible, positive content with tokens and discourages harmful posts by reducing trust scores, creating a transparent, decentralized reputation system for social media.

---

## Features

- **AI Impact Analysis:**  
  Evaluates tweets for potential harm or benefit, using user bios and (optionally) posting history for context.
- **Trust Score Assignment:**  
  Each user receives a dynamic trust score based on the societal impact of their posts.
- **Token Rewards:**  
  Users earn tokens for positive, responsible content.
- **No Negative Scores:**  
  Harmful content does not result in negative scores—minimum is zero.
- **Decentralized & Transparent:**  
  All scores and rewards are recorded on the OriginTrail Decentralized Knowledge Graph (DKG) for auditability.
- **MCP Tool Integration:**  
  Easily connect with agentic frameworks (like Cursor, VS Code, or custom bots) via the Model Context Protocol (MCP).

---

## How It Works

1. **User submits a tweet** to the AI agent (via MCP tool or API).
2. **AI analyzes** the tweet’s potential impact, referencing the user’s bio.
3. **AI returns** an impact/trust score and the number of tokens the user can earn.
4. **User confirms** the post.
5. **AI posts** the tweet on X (Twitter) and issues the reward token.
6. **All actions and scores** are stored on the DKG for transparency.

---

## Example Workflow

1. User:  
   “I want to post: ‘Sleep is important for mental health. Take care of yourself!’”
2. AI:  
   “Impact Score: 95/100. Token Reward: 9. This post is positive and supports mental health awareness. Confirm to post?”
3. User:  
   “Confirm.”
4. AI:  
   - Posts the tweet on X.
   - Issues 9 tokens to the user.
   - Updates the user’s trust score on the DKG.

---

## Sample MCP Tool Usage

```python
/mcp analyze_tweet_by_bio "Sleep is important for mental health. Take care of yourself!" "Certified holistic coach. Empowering you to live better."
```

**Response:**
```json
{
  "impact_score": 95,
  "token_reward": 9,
  "analysis_message": "Based on your bio and tweet, your impact score is 95 and you can earn 9 tokens."
}
```

---

## Getting Started

1. **Clone the repository**
2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
3. **Configure your `.env`** (see `.env.example`)
4. **Run the MCP server**
   ```bash
   python dkg_server.py --transport stdio
   ```
5. **Connect your agent or client** (e.g., Cursor, custom bot) using the MCP configuration.

---

## Roadmap

- [ ] Integrate with X (Twitter) API for automated posting
- [ ] Expand analysis to include user’s posting history and followers
- [ ] Add support for other social platforms
- [ ] Implement advanced NLP for nuanced impact detection
- [ ] Launch token smart contract on blockchain

---

## Contributing

Contributions are welcome! Please open issues or submit pull requests for new features, bug fixes, or improvements.

---

## License

MIT License

---

## Contact

For questions or collaboration, reach out to [your email or contact info].

---

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 dkg_server.py --transport stdio
