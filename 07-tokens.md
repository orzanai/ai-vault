# 07 · TOKENS: see what ChatGPT sees in your messages

From the reel: *"ChatGPT can't read. Here's what it sees instead of your words."* → [@orzan.ai](https://instagram.com/orzan.ai)

The model never gets your letters. It gets numbers, one per **token** (a word or a piece of a word). Facts checked 2026-11-17.

---

## 1. See it yourself: the free token viewer
**[platform.openai.com/tokenizer](https://platform.openai.com/tokenizer)**. Paste any text and it colours every token and shows its id. No account, no code.

Try these:
- `How many r's are in strawberry?` gives **8 tokens**. ` strawberry` is a single token, id **101830** (GPT-4o's tokenizer). One number, no letters, which is a big reason models used to miscount the R's.
- `strawberry` at the very start of a message, with no space before it, becomes `st` · `raw` · `berry`. Same word, different pieces.
- Your name, a long German word, an emoji. Rare words cost more tokens.

## 2. The same thing in 3 lines of Python
```bash
pip install tiktoken
```
```python
import tiktoken
enc = tiktoken.get_encoding("o200k_base")   # the GPT-4o tokenizer, 200,019 tokens
ids = enc.encode("How many r's are in strawberry?")
print(ids, [enc.decode([i]) for i in ids])
# [5299, 1991, 428, 885, 553, 306, 101830, 30]  ['How', ' many', ' r', "'s", ' are', ' in', ' strawberry', '?']
```

## 3. What happens inside, step by step (the reel's six beats)
1. **Tokens.** Your text is cut into tokens and each one becomes an id. On its own, an id means nothing.
2. **Embeddings.** Each id is swapped for a long list of numbers (a vector) that encodes its meaning. Words with similar meanings get similar vectors, which is why "strawberry" sits near "raspberry".
3. **Attention.** Every token looks at every other token and weighs which ones matter for it. In the reel, "strawberry" pays attention to "how many" and "r".
4. **Layers.** Attention plus a small neural network make one layer. Big models stack dozens of them, and each pass refines the vectors.
5. **Scores.** At the end, the model scores every token in its vocabulary (about 200,000 for GPT-4o's tokenizer). One is picked, usually one of the highest.
6. **The loop.** That token is added to the input and the whole thing runs again for the next one. That's why the answer appears word by word.

*The scores shown in the reel are an illustration. Real per-token scores for ChatGPT aren't public.*

## 4. Want to go deeper?
- **3Blue1Brown, Deep Learning chapters 5 and 6** ("Transformers, the tech behind LLMs" and "Attention in transformers"): the best visual walkthroughs of embeddings and attention. All chapters: [3blue1brown.com/topics/neural-networks](https://www.3blue1brown.com/topics/neural-networks).
- **[Transformer Explainer](https://poloclub.github.io/transformer-explainer/)**. Type a sentence and watch a small GPT score its next token, live in your browser.
