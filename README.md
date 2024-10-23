# MultiModal  

Hugginface space application link: https://huggingface.co/spaces/ibrim/MultiModalPhi

Providing 3 examples of the same:

Query 1 -  Image and prompt:

<img width="809" alt="first" src="https://github.com/user-attachments/assets/b19a7317-d6a0-42e0-8b84-fc146503be9f">

Query 2 - Image and prompt with different image:

<img width="1194" alt="second" src="https://github.com/user-attachments/assets/0c13a6be-73bf-4d2c-bc0d-512c51ca8091">

Query 3 - Audio and image query:
Question in audio is "Describe the following image"

<img width="1194" alt="third" src="https://github.com/user-attachments/assets/e0d3b536-7736-4047-b4ce-0287202fc49e">


Assignment Step 1: Pretrain for annotated images.

I have used Coco dataset for pretraining CLIP model (clip-vit-base-patch32) and LLM model (Phi2). 
The following are the training logs:

Example Results:
0 - Target captions:
 There is only room for one person to sit in the chair.  
0 - predicted_captions:
 A living room with a couch,<|endoftext|> 
1 - Target captions:
 A batter keeps his arm loose as he waits at home plate.  
1 - predicted_captions:
 A baseball game with a batter, a pitcher<|endoftext|> 

I have used the machine in my office, hence the proxies. Have taken permission for the same too.


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Assignment Step 2: Finetuning for images and start Q&A mode.

The dataset that I have used is Instruct150k Dataset

The following is the training log:



Example predictions
Image: http://images.cocodataset.org/train2017/000000051587.jpg
Question: Where is the empty suitcase located? [QA]
Answer:   The empty suitcase is located on the wood floor in front of a radiator.<|endoftext|>
Model Predicted Ans:  empty suitcase is located on the floor, next to a bed.

