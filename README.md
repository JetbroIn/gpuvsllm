# Rent or buy, mate?

A one-page static site that asks five questions and tells a company whether to keep renting AI (closed LLM APIs), move into a share house (open-weight models on hosted APIs), buy the house (its own GPUs), or do both.

Don't know your token count? Answer the first question with your monthly OpenAI / Anthropic / Google bill, or with how many agent runs you do a day.

No build step. Open `index.html` or serve the folder:

```sh
python3 -m http.server 8000
```

Results are shareable: answers live in the URL hash (`#v=3.00e10&a=1022`).

Prices and throughput assumptions are in the `P`, `BILL` and `TOKENS_PER_RUN` constants in `index.html`, and listed on the page under "The fine print".

## Analytics

Uses Vercel Web Analytics. Turn it on in the Vercel dashboard under the project's Analytics tab. Page views work on every plan. Custom events (Pro plans): one per question (`Q1 Volume` to `Q5 Traffic`, each with an `answer` property), `Verdict`, `Shared result opened`, `Link copied` and `Start over`. Open an event in the Events panel to see the split of answers.

Made by [@sharvajethwa](https://x.com/sharvajethwa) at [Jetbro](https://www.jetbro.in/).
