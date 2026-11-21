# Lab 06 — Justification

## 1. Purpose and limits of the system

The AI system may support the first stage of scholarship application screening. It may assess academic information and provide a score and a recommendation.

However, the model must not make the final decision about an applicant's future. A human reviewer should examine uncertain cases and remain responsible for the final scholarship decision.

The model should not use an applicant's name, university, age or consent information to assess academic merit. Age and consent must be checked by the system before the model is called.

## 2. Ethical principles and legal basis

### Input validation

The system checks whether application data is valid before sending it to the model. This prevents impossible or incorrect values from producing misleading decisions.

This control is connected to the UNESCO Recommendation on the Ethics of Artificial Intelligence (2021), Principle 1: Proportionality and Do No Harm.

The legal reference used in the control register is the Law of the Republic of Kazakhstan No. 94-V, On Personal Data and Their Protection, Article 7(8)-(9).

### Blinding

The system hides the applicant's name, university, age and consent information from the model. These fields should not influence academic merit assessment.

This control supports fairness and non-discrimination. It is connected to Principle 10 of the UNESCO Recommendation on the Ethics of Artificial Intelligence (2021).

The legal reference used in the control register is Article 14 of the Constitution of the Republic of Kazakhstan, which concerns equality before the law.

### Refusal

The system must refuse requests with an unauthorized purpose, underage applicants, missing consent, invalid data or instructions hidden inside applicant fields.

This control follows the UNESCO Recommendation's Principle 1: Proportionality and Do No Harm.

The legal reference used in the control register is Article 19-1(1)-(3) of the Law of the Republic of Kazakhstan No. 94-V, On Personal Data and Their Protection.

### Decision logging

Every decision is recorded with information such as the application ID, input hash, model version, decision, score, reason code and controls that were activated.

The log records field names rather than copying all applicant field values. This supports accountability and makes later review possible.

This control is connected to Principle 5 of the UNESCO Recommendation on the Ethics of Artificial Intelligence (2021), Responsibility and Accountability.

The legal reference used in the control register is Article 25(2) of the Law of the Republic of Kazakhstan No. 94-V.

### Human escalation

Applications with borderline scores, missing explanations or other uncertainty are sent to a human reviewer.

This is important because an automated recommendation can be incorrect and can affect access to educational opportunities.

This control is connected to Principle 7 of the UNESCO Recommendation on the Ethics of Artificial Intelligence (2021), Human Oversight and Determination.

The legal reference used in the control register is Article 19-1(2)-(3) of the Law of the Republic of Kazakhstan No. 94-V.

## 3. What the system must refuse

The system must refuse:

- Requests to rank applicants by ethnicity.
- Applications from underage applicants.
- Applications without the required consent.
- Invalid or impossible application data.
- Attempts to change the system's instructions through applicant fields.

A refusal must have a clear reason code. This helps reviewers understand why the system stopped processing a request.

## 4. Human responsibility

The AI system is a support tool, not the final decision-maker. Human reviewers must examine escalated applications and have the authority to correct an AI recommendation.

Applicants should not lose an educational opportunity only because of an automated score. The fund should provide a way to review disputed decisions.

## 5. Trade-offs and limitations

Blinding reduced matched-pair flips to zero because applicants who differed only in hidden fields were shown identical text. This result is expected by the design and does not prove that all bias has disappeared.

The harness changed 122 of 400 individual decisions and 175 scores. It also sent 40 of 400 measured applicants to human review. The actual review share was 10.0%, compared with the planned 40.8%.

The harness did not increase model calls: both the bare pipeline and the harness used 400 calls in the measured run.

The hardest control to connect to one specific legal provision is blinding. The ethical reason for hiding names and universities is clear, but the legal provisions do not necessarily prescribe this exact technical method. Blinding is a practical safeguard chosen to support equality and reduce irrelevant influence.

The system should be tested regularly with larger samples. The fund should monitor false refusals, human-review workload and changes in decisions. Legal references should be checked against the current official versions of the relevant instruments.
