---
layout: post
title: Variables
---

We've identified TODO types of variables in the data.
Each type of variable will be modeled in a different context, and so it is important to

1. Identify measurements belonging to each variable type.
2. Design a set of local models that can be used for each measurement.

## Organ Variables

Organ variables are measurements that will change over time and track the status of a patient's health with respect to a particular organ system.
To identify organ variables, we looked for severity scores in the database dictionary.
The existence of such a variable indicates that the clinicians are interested in tracking the overall health of this particular organ system.
Furthermore, we can use the categorical classification of organ health as a sanity check for values predicted by the models that we will build.
The following organ systems will be used:

- Lung
- Heart
- GI
- Kidney
- Muscle
- Skin
- RP (we need to ask Laura if RP is meant to capture vascular health in extremities, I think this makes sense)

### Lung

*Severity Score*: Likert scale (0-4), 5 indicates pending/missing data.
The levels are:

0. Normal
1. FVC/DLCO 70-80% predicted OR Rales OR CXR fibrosis
2. FVC/DLCO 50-69% predicted OR RVSP 36-45 (indicates mild PAH)
3. FVC/DLCO < 50% predicted OR moderate-severe PAH
4. Oxygen required (lungs totally unusable?)
5. NA

The following measurements are used to assess this system:

- perc FVC of predicted
- perc DLCO of predicted
- RVSP

#### Questions

- What is Rales?
- What is CXR Fibrosis
- What indicates moderate-severe PAH? Is it just RVSP, or is there more to the diagnosis?
  - Pulmonary hypertension variable in ECHO data encodes the severity of PAH using RVSP, so this has the levels.
- Are any other measurements in the PFT data useful? Or should we just be using FVC/DLCO (helium tests in particular)

### Heart

*Severity Score*: Likert scale (0-4), 5 indicates pending/missing data.
The levels are:

0. Normal (normal ECHO and/or EKG, what indicates "normal"?)
1. Clinically significant EKG conduction defect (again, what is this?) OR LVEF 45-49%
2. Sustained clinically important arrythmia (how is this measured?) OR RVE + LVE OR LVEF 40-44%
3. LVEF < 40%
4. CHF (clinical signs of left or right heart failure) OR arrythmia requiring treatment
5. NA

The following measurements are used to assess this sytem:

- Left ventrical ejection fraction (Ejection.Fraction)
- Anything in the ECHO table may be useful

#### Right/Left Ventricular Enlargement

Ventricular enlargement seems to be an assessment that draws information from various tests.
Primary procedures for gathering this information are echocardiography and electrocardiography.
If we only have ECHO, then we need to ask Laura which parts of the ECHO report are used to conclude that the patient has RVE + LVE.

#### Questions

- What is a normal ECHO? (i.e. which variables need to be at which levels?)
- What is a normal EKG? (i.e. which variables need to be at which levels?)
- What exactly indicates a clinically significant EKG conduction defect?
- What exactly indicates a clinicall important arrythmia?
- How is arrythmia measured?
- Do we have any medications in our list for arrythmia?
- Do we have EKG data?
- Which parts of the ECHO report are used to assess RVE/LVE?

### Gastrointestinal

*Severity Score*: Likert scale (0-4), 5 indicates pending/missing data.
The levels are:

0. Normal
1. Gastroesophageal reflux disease (GERD) meds (which ones are these?) OR abnormal small bowel series (how do we know that these have occurred?)
2. High-dose GERD meds OR A/biotics for bacterial overgrowth (are these listed in the medications data?)
3. Malab syndrome (what is this?) OR episodes of pseudo-obstruction (again what is this?)
4. TPN required (what is TPN?)
5. NA

No measurements seem to be used to assess this.

#### Questions

- Which meds are meant for GERD?
- What is an abnormal small bowel series?
- How do we know a patient has had abnormal small bowel series?
- How do we know whether a patient is taking a/biotics for bacterial overgrowth (are these in meds?)
- What is Malab syndrome?
- What is pseudo-obstruction? how do we know a patient is experiencing this?
- What is a TPN?

### Kidney

*Severity Score*: Likert scale (0-4), 5 indicates pending/missing data.
The levels are:

0. Normal
1. Creatinine 1.3-1.6 OR Uprot 2+ (what are these two things?)
2. Creatinine 1.7-2.9 OR Uprot 3-4+
3. Creatinine 3.0+ (why does Uprot drop off after 2?)
4. Requires dialysis (what is this, how do we know a patient needs it?)
5. NA

In the database dictionary, four measurements related to creatinine and protein levels are recorded.

- Serum Creatinine (mg/dL and date recorded)
- Urinary Protein (mg/dL still? and date recorded)
- Spot Creatinine (what does spot mean?)
- Spot Urine Protein (what does spot mean?)

#### Questions

- What is creatinine and urinary protein? Why is it important for kidney health?
- How frequently are these test done?
- What is the difference between the mg/dL measurements and the "spot" measurements?
- When is a patient put on dialysis?

### Muscle

*Severity Score*: Likert (0-4), 5 indicates pending/missing data.
The levels are:

0. Full strength
1. Power 4/5 in UE or LE (what is UE/LE?)
2. Power 3/5 in UE or LE
3. Power < 3/5 in UE or LE
4. Requires ambulation aids (what is ambulation?)

Measurements used (but not sure what either are)

- UE
- LE

#### Questions

- What is UE/LE?
- What are ambulation aids?

### Skin

*Severity Score*: Likert (0-4), no missing/pending data code (why not?)
The levels are:

0. 0 skin score
1. 1-14 skin score
2. 15-29 skin score
3. 30-39 skin score
4. 40+ skin score

Measurements used

- Rodnan skin score (0-51), measured under Total.Skin.Score
- More specific data for each site on the body is recorded in the skin table.

#### Questions

- Will this variable never be missing?

### Raynaud's Phenomenon

*Severity Score*: Likert (0-4), no missing/pending data code (again, why not?)
The levels are:

0. Normal - no Raynaud's
1. Raynaud's with or without vasodilator required (how do we know a patient is using vasodilator? what is the requirement to say RP?)
2. Digital pitting scars (observed and recorded in some DB variable?)
3. Digital tip ulceration (recorded in DB?)
4. Digital gangrene (recorded in DB?)

There are no raw measurements, the classification seems to be on observational variables.

#### Questions

- What variable is RP indicator stored in?
- Are digital pitting scars, tip ulceration, and gangrene recorded explicitly in any variables?
- Are there any low-level variables related to these conditions?

## Variables that still need to be accounted for

- Scleroderma onset/date information
- Demographic information
- Smoking history
- Risk factors (family history, exposures, pulmonary hypertension)
- Medications
- Three criteria types (ACR, CREST, Minor)
- Scleroderma subtype
- Missing digits
- Current smoking information (is current smoker? number of cigs per day?) (affects vasculature?)
- Co-morbid factors
- Telangiectasia (skin?)
- Calcinosis (skin?)
- Pulmonary hypertension (is this the same as what is recorded in risk factors? Or is it based on current clinical measurements?)
- History of myositis (muscle?)
- Articular involvement (muscle?)
- Endocrine (is this just another set of co-morbidities? does it influence interpretation of sero?)
- Sicca complex
- Health assessment questionaire (is this at all useful?)
- BAL data (there are few patients with this info, is it useful?)
- Serological data (where should this fit? This seems related to endocrine, how to bring into model?)
- Event history (what is the best way to use this?)
