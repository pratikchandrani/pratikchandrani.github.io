---
layout: post
title: "More than 12,000 Studies. 1,400 Plants. One Question: Can Traditional Medicine Help Us Fight Cancer?"
date: 2026-02-25
author: Isha Shinde, Ninad Dhumak, Pratik Chandrani
tags:
  - Ayurveda
  - Computational Biology
  - Artificial Intelligence
  - Indian Traditional Medicine
excerpt: How we built NatureCAN—one of the first AI-curated evidence-based traditional medicine to modern cancer research.
---

Somewhere in a laboratory in Hong Kong, a team finds that Andrographis paniculata (a plant commonly known as Kalmegh in India) has activity against oesophageal cancer [1]. In Japan, a researcher discovers that a compound from Euphorbia tirucalli (locally known as Barki-thohar or Sher-kandvel in India) kills Burkitt’s lymphoma cells [2]. In India, a preclinical study shows that mitocurcumin (a curcumin derivative obtained from turmeric) induces mitophagy in leukaemia cells [3].
None of these researchers probably knows about each other’s work, and none likely knows that these plants have been used in Indian traditional medicine for centuries. Their findings are scattered across thousands of journals, buried under paywalls, written in the dense dialect of molecular biology. And yet, taken together, they tell a remarkable story: traditional medicinal plants are not just folklore—they are being validated, one experiment at a time, by modern science.
The problem is that nobody has connected the dots. Until now.

---

## Cancer treatments -- a side effect problem nobody talks about
Cancer is not one disease. It is hundreds of diseases wearing the same name, each driven by a different combination of genetic mutations, environmental exposures, and lifestyle factors. Treating it demands powerful interventions—chemotherapy, radiation, immunotherapy, surgery—and these interventions save lives every day. But they come at a cost that anyone who has watched a loved one go through treatment understands viscerally: nausea that makes eating impossible, fatigue so deep it feels like gravity has doubled, nerve damage in the hands and feet, a weakened immune system that turns a common cold into a hospital visit. [4, 5]

This is where traditional medicine—Ayurveda, in particular—enters the conversation. Not as a replacement for chemotherapy. Not as a miracle cure. But as a companion that might ease the journey. Ayurveda, the 3,000-year-old Indian system of medicine, approaches health through balance—of the body’s three fundamental energies (doshas), of diet and digestion, of mind and immunity. Instead of targeting one molecule in one pathway, Ayurvedic preparations often work on multiple fronts simultaneously—a trait that, as it turns out, modern pharmacology is beginning to appreciate [6].

---

## Thousands of Studies, No Map
Here is the uncomfortable truth: the scientific evidence for medicinal plants in cancer care does exist—lots of it—but it is fractured across tens of thousands of PubMed articles, each written for specialists in a narrow subfield.  Manual curation—reading and categorizing these articles by hand—remains the gold standard, but it is crushingly slow. A single researcher might spend months reviewing literature on just one plant. Multiply that by the 4,000+ medicinal plants catalogued in India’s IMPPAT database, and you begin to see the scale of the challenge.

We decided to tackle it differently.

We have developed NatureCAN—an evidence-based knowledge base focused on medicinal plants in cancer care. NatureCAN enables users to search for any medicinal plant and access comprehensive evidence on its use in cancer, including cancer-type curation, study models, experimental techniques, and toxicity data. Without getting into the nitty-gritty of the technical setup, let’s see a case study.

<figure style="text-align: center; margin: 2em 0;">
<img src="/assets/img/blog/NatureCAN_workflow.png" alt="A thematic workflow of NatureCAN database development" style="max-width: 100%; height: auto;">
<figcaption style="font-size: 0.85em; color: #666; margin-top: 0.5em;"><strong>Figure 1.</strong>A thematic workflow of NatureCAN database development.</em></figcaption>
</figure>

NatureCAN currently covers 12,682 research articles spanning 1,496 medicinal plants. For each article, users can explore which cancer types were investigated, what model systems were used (human cell lines, animal models, or human patients), and whether any safety or toxicity data was reported. It is, as far as we know, the most comprehensive structured evidence base of its kind. For example, one can search for Curcuma Longa (turmeric) in NatureCAN and find more than 600 articles, as shown in the following barplot:

<figure style="text-align: center; margin: 2em 0;">
<img src="/assets/img/blog/NatureCAN_Curcuma_barchart.png" alt="A bar chart depicting number of publications of Curcuma longa in cancer for each category of modern biological study" style="max-width: 100%; height: auto;">
<figcaption style="font-size: 0.85em; color: #666; margin-top: 0.5em;"><strong>Figure 2.</strong>A bar chart depicting number of publications of Curcuma longa in cancer for each category of modern biological study.</em></figcaption>
</figure>


A total of 622 articles on Curcuma longa include more than 350 in vitro experiments, 100 in vivo studies, 150 reviews, and about 20 clinical trials. What makes curcumin’s story so interesting is its breadth. The NatureCAN data shows it has been studied against at least 55 distinct cancer types—from common malignancies like breast, colon, and lung cancer to rare ones like cholangiocarcinoma and Burkitt’s lymphoma. Interestingly, clinical trial data show compelling evidence in breast cancer and colorectal cancer, while most other cancer types are yet to be tested through clinical trials. Similarly, users interested in specific cancer type, laboratory model, phytochemical can also find specific evidence using NatureCAN. This is precisely the kind of data NatureCAN makes visible: the promise is real, but the road from laboratory to bedside is long, and the bottleneck is clinical, not biological.

---

## Indian Traditional Medicine, Modern Proof

Let us be clear about what NatureCAN is and what it is not. It is not a prescription tool. It does not claim that any plant can cure cancer. What it does is make the evidence visible—organized, structured, and honest about its limitations. The steep pyramid from 10,000 lab studies down to 300 clinical trials is the scientific process working as it should, slowly and carefully.
What NatureCAN reveals is that the ancient pharmacopoeia is not waiting to be discovered—it is waiting to be properly tested. The compounds are there. The biological mechanisms are increasingly understood. What the field needs now is more well-designed human studies, better formulation science to overcome bioavailability hurdles, and the kind of structured, accessible evidence base that lets researchers and clinicians make informed decisions.

NatureCAN is our contribution to that effort—a step toward illuminating ancient science through modern, data-driven validation for cancer care.

Happy Sciencing!

<strong>Credits:</strong> This work was conducted in collaboration with Dr. Vikram Gota, Dr. Archana Redhu, Dr. Priyanka Singh at <a href="https://clinicalpharmacolo9.wixsite.com/department-of-clinic">Clinical Pharmacology</a> at ACTREC. We acknowledge the funding support from <a href="https://dbtindia.gov.in/">Department of Biotechnology</a> (DBT: BT/PR40181/BTIS/137/15/2021, BT/PR40231/BTIS/137/63/2023, BT/PR50410/MED/12/1122/2023) and <a href="https://ayush.gov.in/">Ministry of Ayush</a>. Visit the <a href="https://pratikchandrani.github.io/">Chandrani lab</a> website for more interesting research.

<strong>References:</strong>
1.	Chiu, P.W., et al., The effect of Andrographis paniculata water extract on palliative management of metastatic esophageal squamous cell carcinoma-A phase II clinical trial. Phytother Res, 2023. 37(8): p. 3438-3452.
2.	Aya, T., et al., Chromosome translocation and c-MYC activation by Epstein-Barr virus and Euphorbia tirucalli in B lymphocytes. Lancet, 1991. 337(8751): p. 1190.
3.	Gaur, T., et al., Mitocurcumin utilizes oxidative stress to upregulate JNK/p38 signaling and overcomes Cytarabine resistance in acute myeloid leukemia. Cell Signal, 2024. 114: p. 111004.
4.	Bota, M., et al., Exploring Synergistic Interactions between Natural Compounds and Conventional Chemotherapeutic Drugs in Preclinical Models of Lung Cancer. Pharmaceuticals (Basel), 2024. 17(5).
5.	Arnold, J.T., Integrating ayurvedic medicine into cancer research programs part 2: Ayurvedic herbs and research opportunities. J Ayurveda Integr Med, 2023. 14(2): p. 100677.
6.	Sulaiman, C., B.P. George, I. Balachandran, and H. Abrahamse, Cancer and Traditional Medicine: An Integrative Approach. Pharmaceuticals (Basel), 2025. 18(5).

