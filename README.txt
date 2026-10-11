# HOME CREDIT - AI VOICE AGENT FOR LOAN AGAINST PROPERTY (LAP) QUALIFICATION
================================================================================

1. PROJECT OVERVIEW
-------------------
This project implements an outbound AI Voice Agent designed for "Home Credit" 
to contact existing loyalty customers, inform them of an exclusive pre-approved 
Loan Against Property (LAP) offer up to ₹75,00,000 (75 Lakhs), evaluate 7 eligibility 
criteria sequentially, immediately disqualify ineligible applicants, handle loan 
transfers/EMI reductions, and route qualified leads to a senior human loan expert.


2. CORE CAPABILITIES & LOGIC
-----------------------------
- Natural, Human-like Conversational Voice (1-2 sentences per turn, spoken cadence).
- Dynamic State Tracker: Extracts multiple entities in a single utterance; handles
  out-of-order information and avoids re-asking previously answered questions.
- Immediate Disqualification Policy: Zero-tolerance immediate exit if a customer has:
  * Agricultural land
  * Income received in Cash
  * Unavailable original property title documents
  * Tenure outside the 3 to 15-year window
- Transfer Logic Switch: If the customer has an existing loan or seeks EMI reduction, 
  the agent immediately transfers the case to a loan-transfer specialist.
- Soft-Cap Loan Negotiation: If the customer requests > ₹75 Lakhs, offers the maximum
  cap of ₹75 Lakhs.
- RAG / Diversion Handling: Deflects interest rate queries to the senior human loan expert
  without hallucinating figures.


3. THE 7 ELIGIBILITY CRITERIA
------------------------------
1. Property Type: Residential, Commercial, Industrial (Eligible); Agricultural (Disqualify).
2. Ownership Status: Sole ownership or Joint ownership (Both Eligible).
3. Document Availability: Original documents available for verification (Required).
4. Loan Amount: Up to ₹75,00,000 (75 Lakhs).
5. Occupation & Income Mode: Salaried or Self-Employed + Bank Transfer (Eligible); Cash (Disqualify).
6. Property Market Value: Estimated value captured (no minimum threshold).
7. Tenure: 3 to 15 years (Eligible); <3 or >15 years (Disqualify).


4. FILES IN THIS SUBMISSION
----------------------------
- system_prompt.txt: Complete, production-ready system prompt with state logic.
- README.txt: Overview, rules, and architecture summary.
- transcripts.txt: Complete logs of all test scenarios executed on the voice platform.
- ARCHITECTURE_APPROACH.md: Deep dive into the 5-layer conversational state architecture.


5. PLATFORM SETUP & DEPLOYMENT
-------------------------------
- Platform: Retell AI (Single-Prompt Agent architecture)
- LLM Engine: GPT-4o / GPT-5.6 Terra
- Voice: Professional Indian English (e.g., Aditi / natural neutral female voice)
- Initial Greeting: "Hello, good afternoon, am I speaking with Rahul Sharma?"
