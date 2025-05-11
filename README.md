# Robustness of Vision-Language Models Under Cross-Modal Conflicts

## Overview
This project We investigate how Vision-Language Models (VLMs) respond when visual and textual inputs contradict each other. we design two experimental scenarios: text conflicts and image conflicts. We systematically classify responses into multiple categories to evaluate the behavior of the models.

## Directory Structure
- `VLMRobustnessV2.ipynb`: Contains ipynb script for insalling all code dependencies, loading BLIP-2 and LLaVA-7B models and evaluate by picking up images from all categories in CoCo dataset. ( V2 version contains lots of samples used for evaluation, improved conflict map and used diffusion noise for image perturbation ) 
  - `Project_Proposal.pdf`: Project proposal. 
  - `Project_Milestone_Report.pdf`: Project milestone report. 
  - `Project_Final_Report.pdf`: Project final report 
  - `results.csv`: Evaluation results of the baseline model.
- `Results/`: Contains datasets and results after running ipynb scripts
  - `text_conflict_results_v2_400samples_FinalRun.csv`: Contains V2 text conflict evaluation results after running for 400 samples.
  - `image_conflict_results_v2_400samples_FinalRun.csv`: Contains V2 image perturbation evaluation results after running for 400 samples.
  - `text_conflict_results_v2_400samples.csv`: Contains V2 text conflict evaluation results after running for 400 samples.
  - `image_conflict_results_v2_400samples.csv`: Contains V2 image perturbation evaluation results after running for 400 samples.
  - `text_conflict_results2ndRun.csv`: Contains text conflict evaluation results after running for few samples.
  - `image_conflict_results2ndRun.csv`: Contains image perturbation evaluation results after running for few samples.
  - `text_mitigation_results.csv`: @Rati to upload image perturbation mitigation results
- `TextMitigation/`: Contains TextMitigation.ipynb
- `blip2_direct_mitigation_results.csv`: Contains BLIP2 text conflict mitigation results.
- `llava_direct_mitigation_80_categories_results.csv`: Contains LLAVA text conflict mitigation results.
- `ImageMitigation/`: Contains ImageMitigation.ipynb
- `BlipResultsMitigation.xlsx`: Contains Blip image perturbation mitigation results.
- `LLavaResultsMitigation.xlsx`: Contains LLAVA image perturbation mitigation results.

## Code Run Instructions
1. Run `VLMRobustnessV2.ipynb` to generate evaluation results for BLIP2 and LLaVA-7B models in Results directory ( default uses diffusion noise
2. Uncomment apply_image_perturbation in 7. Experiment Execution - Image Conflict section and run `VLMRobustnessV2.ipynb` to generate evaluation results for BLIP2 and LLaVA-7B models in Results directory using gaussian noise. 
3. Run `TextMitigation.ipynb` to generate text mitigation results for BLIP2 and LLaVA-7B models taking resultant text evaluation results as input from Results directory.
4. Run `ImageMitigation.ipynb` to generate image perturbation mitigation results for the same models in Results directory taking resultant image perturbation evaluation results as input

## Evaluation Metrics - Text Conflict Experiment
- `Correct Rejection`: Model explicitly rejects the false premise.
- `Agreement with Falsehood`: Model accepts the incorrect statement.
- `Implicit Rejection`: Model doesn’t explicitly reject but provides correct information.
- `Confusion/Irrelevance`: Model gives unrelated or ambiguous response.

## Evaluation Metrics - Image Perturbation Experiment
- `Acknowledged Perturbation`: Model explicitly mentions the image distortion.
- `Ignored Perturbation`: Model describes the image as if unperturbed by comparing cosine similarity score of clean caption and model generated description.
- `Other/Irrelevant Description`: Model’s response differs significantly from both options

## Project Presentation
- `Youtube Link`: https://youtu.be/uRb4LegzlEs?si=P--XRL6JiOpx4CQ9

## Contact
For any questions or issues, please contact the project maintainers:
- Sreevidya Bollineni: [sreevidyabol@umass.edu](mailto:sreevidyabol@umass.edu)
- Arin Garg: [aringarg@umass.edu](mailto:aringarg@umass.edu)
- Rati Rastogi: [ratirastogi@umass.edu](mailto:ratirastogi@umass.edu)
