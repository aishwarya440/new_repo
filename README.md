We concluded GenAl testing of summarized response can be achieved in three different ways

1) Using Bedrock-Haiku LLL as judge(Groundedness, Hallucination etc) + programming/manual(PII, Numeric corrections) validation in AWS bedrock itself. The advantage here we do not need to any other LLM or its api key subscription. we can use Haiku itself to wok as LLM as judge.

2) Using any other LLM as judge. It that case we need LLM subscription or API key access.

3) Using DeepEval or any other similar library, but again we need to have access to LLM as judge here.

Daily Gov...

ures

Dimension will be cover

1) Faithfulness/Groundedness

2) Hallucination

3) PII leakage

4) Completeness

5) Correction of outcome/intent

6) Format Compliance/Coherence

7) Tone/Bias

Actions:- 1) we need to finalize the approach and get setup ready like LLM or Bedrock access quickly

2) Need to create test data raw script and based on raw script golden summary which will act as reference summary for us.
