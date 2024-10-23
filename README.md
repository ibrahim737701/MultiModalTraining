# Making Microsoft PHI MultiModal 

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

## Part 1: Image Embeddings with CLIP and Phi Model

In this part of the project, I integrated CLIP model (vit-base-patch32) to generate image embeddings. These embeddings were either computed in real-time since I had enough compute. I then added a projection layer to convert these image embeddings into a format compatible with the text embeddings of the Phi model. By concatenating these embeddings, the model gained the ability to understand and reason about visual inputs alongside text.

Link to the training logs:-
https://github.com/ibrahim737701/MultiModalTraining/blob/3acfd63a3e64def8e64ab49abf7fe56d9faa9fce/Model_pretrain/training_logs_20241009_102342.txt

Example Results:
0 - Target captions:
 A group of teddy bears are on display at the store.<|endoftext|><|endoftext|><|endoftext|><|endoftext|><|endoftext|><|endoftext|><|endoftext|><|endoftext|>  
0 - predicted_captions:
 A display of stuffed animals in a store...........<|endoftext|> 
1 - Target captions:
 A man holding a tennis racquet on a tennis court.  
1 - predicted_captions:
 A man is playing tennis on a court.<|endoftext|>


<img width="635" alt="image" src="https://github.com/user-attachments/assets/52f2aa4f-583a-411e-bcc5-dc9f752eb298">

I have used the machine in my office, hence the proxies in the code. Have taken permission for the same too.


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Part 2: Fine-Tuning with PEFT QLORA


Building on the initial model, I fine-tuned it using PEFT (Parameter-Efficient Fine-Tuning) and QLORA techniques on the Instruct 150k dataset. This process optimized the model's capability to answer questions by learning more contextual and task-specific representations. The goal was to enhance the performance of the model while keeping the additional fine-tuning parameters small, resulting in a more efficient, versatile question-answering model.

The following is the training log:

https://github.com/ibrahim737701/MultiModalTraining/blob/3acfd63a3e64def8e64ab49abf7fe56d9faa9fce/Finetune/log.txt

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Part 3: Add whisper to pipeline and host app

In the final part of the project, I incorporated OpenAI's Whisper ASR model into the pipeline. This allowed the model to accept audio inputs, converting them to text via automatic speech recognition (ASR). By stitching Whisper into the pipeline, the model was capable of handling multimodal input—enabling a seamless transition from image and text inputs to audio, offering a comprehensive user interaction experience.
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Future improvements:

I could've used techniques like OneCyclePolicy to speed up the training process. 
Mixed precision training.
Could have tried SGD instead of ADAM.




