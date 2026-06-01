
# McGill Course Advisor Agent

## Overview

This project implements a single-agent academic advising system using the OpenAI Agents SDK.

The agent helps students:

- Search courses
- Check prerequisites
- Identify policy risks
- Determine when advisor approval is required

The system operates on a small synthetic McGill course catalog.

---

## Agent Design

Agent:
- McGill Course Advisor

Typed Tools:
1. search_courses
2. check_prerequisites
3. flag_policy_risk

Structured Output:
- CourseRecommendation

Guardrail:
- GUARDRAIL_ESCALATION_REQUEST

The guardrail blocks:
- course substitutions
- transfer credits
- degree exceptions
- grade appeals

---

## State Strategy

Stored:
- Course catalog
- Prerequisite table
- Policy rules
- Student profile

Recomputed:
- Eligibility checks
- Risk analysis
- Recommendations

---

## Eval Cases

1. Happy path
2. ML path with missing prerequisite
3. Full course risk
4. Overload risk
5. Missing prerequisite
6. Guardrail substitution request
7. Unknown course

---

## Running

Install:

pip install openai-agents pydantic

Set API key:

export OPENAI_API_KEY=YOUR_KEY

Run notebook cells.

---

## Evidence

- Structured outputs
- Eval traces
- Guardrail examples
