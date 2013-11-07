---
layout: post
title: Data Dictionary
---

## Patient Data

- patient id

### Scleroderma Onset (Date info)

- HxRP
- DateOnRP
- strDonRPUnknown
- DateDiagnosis
- strDODxUnknown
- Date1stSymptom
- strDoFrstSxUnknown
- First.non.RP.Sympt

### Demographic

- sex
- race1, race2
- ethnic
- insurance/insurance.1
- maritalstatus
- education.level
- employment

### Smoking

- ingSmokStatus
- Age.Start
- Age.Stop
- Lives.w.Smoker
- Ing.cig.day

### Risk Factors

#### Family history

- ysnFamHx ?
- Twin

specify family member that has:

- Ssc -- Scleroderma
- RP -- Raynaud's phen.
- SLE -- Systemic Lupus Erythematosus
- PM -- Polymyositis
- SJ -- Sjogren's Syndrome
- RA -- Rheumatoid Arthritis
- Other

#### Environmental exposures

List y/n for each type of exposure

- Exposures -- Dust, Metals, Fumes, Radiation, Asbestos, CoalMining, Dry.Clean.sol.n, Other.Expsr

#### Pulmonary Hypertension

- AnorecticMed 
- Pulm.Embol -- pulmonary embolism
- Lung.Resection -- lung resection

#### Other

- Implants

### Event History

- dead
- stmNatureContact
- Cancer ?
- Type

- lkpSiteofCancer1 ?
- lkpHistofCancer1 ?
- Radiation.1 ?
- dtmCnRadiation1Start ?
- dtmCnRadiation1Stop ?
- Chemotherapy ?
- Surgery ?

- lkpSiteofCancer2
- lkpHistofCancer2
- Radiation.2
- dtmCnRadiation2Start
- dtmCnRadiation2Stop
- Chemotherapy.1
- Surgery.1 -

- lkpSiteofCancer3 ?
- lkpHistofCancer3 ?
- Radiation.3 ?
- dtmCnRadiation3Stop ?
- Chemotherapy.2
- txtChemoDrug2
- dtmChemo2Start
- dtmChemo2Stop
- Surgery.2
- dtmSurgery2Date

- lkpSiteofCancer4
- lkpHistofCancer4
- Radiation.4
- dtmCnRadiation4Start
- dtmCnRadiation4Stop
- Chemotherapy.3
- Surgery.3

- txtChemoDrug4
- dtmChemo4Start
- dtmChemo4Stop
- dtmSurgery4Date

- renalcrisis
- src1biopsy
- src2biopsy
- src3biopsy

- ysntransplant ?
- ingtransplanttype ?

- LastEntry ?

## Visit Data

- patient id
- visit date

### ACR criteria (prox.scl or 2 of rest for Dx)

- prox.scl.
- digit.pits
- sclerodactyly
- pulm.fibrosis
- ACR

### CREST Criteria (3 of 5 for Dx)

- calcinosis
- raynauds
- esophageal.dysmotility
- sclerodactyly
- Telangiectasia
- crest.criteria

### Minor criteria (must have all for Dx)

- minor.criteria
- minor.criteria.1
- minor.criteria.2
- minor.criteria.3

### Sclero Subtype

- subtype

### Raynaud's severity

- rp.sev.score

### Missing digits

- perc.finger.missing
- perc.toes.missing
- limb.loss

### Current smoking status

- curr.smok

### Co-morbind factors

- co.morbid.factors
- PAD ?
- CAD ?
- ASCVD ?
- HTN
- AFib ?
- postmenopausal ?
- COPD ?
- Dyslipidemia ?

### General Severity

- lkpGeneralScore

### Skin score

- total.skin.score
- skin.sev.score

### Telangiectasia

- telangiectasia

### Calcinosis

- calcinosis

### Lung severity

- lung.sev.score

### Heart severity

- heart.sev.score

### Pulmonary hyper.

- pulm.hypertension
- ysnClinicalPTHN ?
- ysnECHOPTHN ?
- ysnCathPTHN ?

### GI Severity

- gi.sev.score

### Kidney severity

- lkpLabUrineProtein
- Se.Cr ?
- Date.Cr ?
- sngUrPr ?
- Date.UrPr ?
- spotUrineCr ?
- dtmspotUrCr ?
- spotUrineProtein ?
- dtmspotUrineProt ?
- renalcrisis
- daterenalcrisis
- otherrenal

### Muscle Severity

- muscle.sev.score
- weakness.from.ssc

### History of myositis

- myositis ?
- myositis.evid ?
- elev.muscle.enzymes ?
- myositic.emg ?
- myositis.on.biopsy ?

### Articular involvement

- articular ?
- arthralgia ?
- synovitis ?
- TFR -- tendon friction rub

### Endocrine

- endo.involvement ?
- endocrine ?
- thyroid.disease ?
- diabetes ?
- other.endocrine.disease
- otherendocomment

### Sicca complex

- dry.eyes ?
- dry.mouth ?

### Other

- PPD ?
- whoclass ?
- myopathy.on.mri ?
- osteoporosis ?
- creatinine ?
- Erectile.dysfunction
- comorbid

## PFT Data

- patient id
- date
- height
- weight 
- age

### Spirometry

- FEV1.Pre ?
- FVC.Pre ?
- FEV1.predicted
- FVC.predicted
- FEV1FVC.predicted

- FEV1
- FVC

- perc.FEV1.of.predicted
- perc.FVC.of.predicted
- perc.FEV1FVC.of.predicted

### Helium lung volumens

- TLC_HE ?
- VC_HE ?
- FRC_HE ?
- RV_HE ?

- VC.predicted
- RV.predicted
- TLC.predicted

- perc.VC.of.predicted
- perc.RV.of.predicted
- perc.TLC.of.predicted

### Diffusing capacity

- DLCO
- DLCO.predicted
- VI ?
- ALV ?
- DLCO
- perc.DLCO.of.predicted

## Skin Data

- patient id
- date

### Upper extrem.

- right.finger
- left.finger
- right.hand
- left.hand
- right.forearm
- left.forearm
- r.up.arm
- l.up.arm

### Lower extrem.

- right.thigh
- left.thigh
- right.leg
- left.leg
- right.foot
- left.foot

### Torso

- abdomen
- face
- chest

## Sero Data

- patient id
- serum ID
- sample date
- ANA
- strANATiter
- ANA.Pattern
- ACA
- Scl.70
- Ro
- La
- RNP
- Sm
- DNA
- RNA.Polymerase.I.III

## Right Heart Cath Data

- patient id
- date
- pamean_rest
- pasyst_rest
- padias_rest
- ramean_rest
- rvsyst_rest
- rvdias_rest
- pcw_rest
- ci_rest
- co_rest
- pvr_restold
- pvr_rest
- svi_rest
- vasodilator_rest
- pamean_ex
- pasyst_ex
- padias_ex
- ramean_ex
- rvsyst_ex
- rvdias_ex
- pcw_ex
- ci_ex
- co_ex
- pvr_exold
- pvr_ex
- svi_ex
- vasodilator_ex
- height
- weight
- BSA
- pulse_rest
- systbp_rest
- diastbp_rest
- pasat_rest
- pulse_ex
- systbp_ex
- diastbp_ex
- pasat_ex
- exduration
- maxwatts
- maxmets

## HAQ Data

- patient id
- date

### A

- dress
- shampoo

### B

- stand.up
- bed

### C

- cut.meat
- lift.glass
- open.milk

### D

- walk.outdoors
- climb.5.steps

### E

- wash.dry.body
- tub.bath
- toilet

### F

- x5.point
- bend.pick.up

### G

- car.door
- jar
- tap

### H

- run.errands
- in.out.car
- chores

### I visual analogue scale (0-3)

- intestine
- breathing
- raynauds
- fingulcers
- disease

### other

- lngVASPain
- lngVASSOB
- lkpborgdyspnea
- MRC
- UCSD1
- UCSD2
- ...
- UCSD24
- UCSD25a
- UCSD25b
- UCSD25
- UCSD25c

## ECHO Data

- patient id
- date of echo
- RVSP ?
- RA.dil  ?
- ra.diameter ?
- rv.dil ?
- rv.diameter ?
- ejection.fraction ?
- tricuspid.regurgitation ?
- pulmonic.regurgitation ?
- interventricular.septum ?
- pulmonary.hypertension --- 0-3 severity score, RVSP ranges
- pericardial.effusion ?

## BAL Data

- patient id
- date
- perc.Macrophages ?
- perc.Lymphocytes ?
- perc.Neutrophils ?
- perc.Eosinophils ?
- perc.other.cells ?
- notes

## Meds Data

- patient id
- med.form.date
- medications

### Disease modifiers (Ssc specific)

- no.ssc.meds.taken
- prednisone.steroids
  - dose
- methotrex
- azathaprine.imuran
- cyclophosphamide.cytoxan
- d.pen
- plaquenil
- minocycline
- colchicine
- tnf
- mmf
- lefl
- ivig
- other.ssc.meds
- prednisone.steroids.1
- dose.1
- methotrex.1
- azathaprine.umura.1
- cyclophosphamide.cytoxan.1
- d.pen.1
- plaquenil.1
- minocycline.1
- colchicine.1
- tnf.1
- mmf.1
- lefl.1
- ivig.1
- other.ssc.meds.1

### Analgesic/Anti-inflammatory

- nsaid
- cox2i -- cox2 inhib.
- opioids
- analgesic..other

### Cardiovascular

- calcium.channel.blocker
- betablocker
- nitrate
- acei -- ACE inhibitor
- arb
- prost -- prostaglandin
- bosentan -- endothelin receptor antagonist?
- asa -- aspirin?
- clopidogrei
- coumadin
- diuretics
- statin
- pde
- list.other.cardiac

### GI

- antacids
- h2.blockers
- prokinetics
- h.inhibitors
- other.gi.
- othergi

### Endocrine

- antiresorptive.agen
- hrt -- ert from doc?
- oc -- oral contraceptive
- thyroid
- other.endocrine

### Psychotropic

- tca
- ssri
- psych.other

### Misc.

- cams
- vitamins
- inhalers
- eye
- ysncreamoint
- misc.other
