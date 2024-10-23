# era_capstone

The following is the link of the final hugging face application
https://huggingface.co/spaces/saurabhmangal12/Multimodal_LLM_ERA

Providing 2 examples of the same:

Query 1



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

