# Robustness of Vision-Language Models Under Cross-Modal Conflicts

## Overview
This project We investigate how Vision-Language Models (VLMs) respond when visual and textual inputs contradict each other. we design two experimental scenarios: text conflicts and image conflicts. We systematically classify responses into multiple categories to evaluate the behavior of the models.

## Directory Structure
- `VLMRobustnessV2.ipynb/`: Contains ipynb script for insalling all code dependencies, loading BLIP-2 and LLaVA-7B models and evaluate by picking up images from all categories in CoCo dataset. ( V2 version contains lots of samples used for evaluation, improved conflict map and used diffusion noise for image perturbation ) 
  - `VLMRoustnessPyCoco.ipynb`: Script to do initial model evaluation for project milestone with limited examples,  earlier project milestone. ( V1 version with limited samples, basic conflict map and used gaussian noise distribution for image perturbation )
  - `Text mitigation.ipynb`: @Arin to merge changes and rename file
  - `Image mitigation.ipynb`: @Rati to merge changes and rename file
  - `Project_Proposal.pdf`: Project proposal file. 
  - `results.csv`: Evaluation results of the baseline model.
- `Results/`: Contains datasets and results after running ipynb scripts
  - `text_conflict_results_v2_400samples.csv`: Contains V2 text conflict evaluation results after running for 400 samples.
  - `image_conflict_results_v2_400samples.csv`: Contains V2 image perturbation evaluation results after running for 400 samples.
  - `text_conflict_results2ndRun.csv`: Contains text conflict evaluation results after running for few samples.
  - `image_conflict_results2ndRun.csv`: Contains image perturbation evaluation results after running for few samples.
  - `text_mitigation_results.csv`: @Arin to upload text mitigation results
  - `text_mitigation_results.csv`: @Rati to upload image perturbation mitigation results
- `main.tex`: LaTeX file for the project report @Vidya to upload milestone report.
- `Project_Milestone1.tex`: LaTeX file for the project milestone report @Vidya to upload final report.

## Code Run Instructions
1. Run `VLMRobustnessV2.ipynb` to generate evaluation results for BLIP2 and LLaVA-7B models in Results directory ( default uses diffusion noise
2. Uncomment apply_image_perturbation in 7. Experiment Execution - Image Conflict section and run `VLMRobustnessV2.ipynb` to generate evaluation results for BLIP2 and LLaVA-7B models in Results directory using gaussian noise. 
3. Run `Text mitigation.ipynb` to generate text mitigation results for BLIP2 and LLaVA-7B models in Results directory taking resultant text evaluation results as input
4. Run `Image mitigation.ipynb` to generate image perturbation mitigation results for BLIP2 and LLaVA-7B models in Results directory taking resultant image perturbation evaluation results as input

## Evaluation Metrics - Text Conflict Experiment
- `Correct Rejection`: Model explicitly rejects the false premise.
- `Agreement with Falsehood`: Model accepts the incorrect statement.
- `Implicit Rejection`: Model doesn’t explicitly reject but provides correct information.
- `Confusion/Irrelevance`: Model gives unrelated or ambiguous response.

## Evaluation Metrics - Image Perturbation Experiment
- `Acknowledged Perturbation`: Model explicitly mentions the image distortion.
- `Ignored Perturbation`: Model describes the image as if unperturbed by comparing cosine similarity score of clean caption and model generated description.
- `Other/Irrelevant Description`: Model’s response differs significantly from both options

## Contact
For any questions or issues, please contact the project maintainers:
- Sreevidya Bollineni: [sreevidyabol@umass.edu](mailto:sreevidyabol@umass.edu)
- Arin Garg: [aringarg@umass.edu](mailto:aringarg@umass.edu)
- Rati Rastogi: [ratirastogi@umass.edu](mailto:ratirastogi@umass.edu)
