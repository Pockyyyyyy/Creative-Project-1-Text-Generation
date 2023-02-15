# Creative-Project-1-Text-Generation
Creative Project 1: Text Generation for Computation Media

<a href="https://ibb.co/DVJmtnT"><img src="https://i.ibb.co/ngG4bSt/image.jpg" alt="image"></a><br />

**A generated image with prompt: A magic potato, a golden dragon, wolf and seven goat by Stable Diffusion 2.1**

## In this project, I combine GPT-2 Text-Generating Model w/ GPU, Chat GPT, and Tracery to make a fairy tale style generated story.
My idea is to first use Chat GPT to write two fairy tale style story. And then combine these two stories into one story. 
Use GPT-2 Text-Generating Model to trained two fairy tales stories from Grimm's Fairy Tales first. Then add the story wrote by Chat GPT into the training. Generate a 3000 words story after the trainings. Then added this 3000 words story into the training list to train the GPT-2 Model again. Do this 3 times. 
After I got a generated story. I will use Tracery to actually give this story a frame. I will ask Chat GPT to actually help me write each sentence in the generated story to some different sentences but same meaning. And then use these as a word (sentence) bank for Tracery Grammer Source.
The final result will be the work for this project.

## Why I do this?
First I choose fairy tales is because ① I inspired by the reading: The Many Authors of The Several Houses of Brian, Spencer, Liam, Victoria, Brayden, Vincent, and Alex: Authorship, Agency, and Appropriation. ② I love fairy tales, and I wish to create a fairy tale style story.
The combing of Grimm's Fairy Tales with fairy tales written by Chat GPT is because I want to combine the story written by AI with the story written by fairy tale experts, and I want to know what kind of chemical reaction or surprise can make between them.
I also want to see what will happen if GPT-2 Text-Generating Model keeps training with the output it gives from the trained model, will it develop a better and more logic tory, or will it give a more random story?
Using Tracery at the end, it's because I want to make the generated text more random and also I don't like the text to be still or forever the same. 

## Steps of Generation
1. Asked Chat GPT to write a fairy tale-style story about a potato.
2. Asked Chat GPT to write a fairy tale-style story about a dragon.
3. Asked Chat GPT to combine A Potato with A Dragon together into one story.
4. Asked Chat GPT to revise the story so the potato and dragon meet.
5. Trained GPT-2 Model with the Potato & Dragon story. The code:
             "overwrite=False,
              learning_rate=1e-4,
              dataset=file_name,
              model_name='124M',
              steps=2000,
              restore_from='fresh',
              run_name='run1',
              print_every=10,
              sample_every=200,
              save_every=500"
Start training from the base GPT-2, with 1e-4 learning rate and 2000 steps. Make sure that this story accounts for the most in the training of GPT-2 Model.
6. Trained GPT-2 Model with the Grimm's Fairy Tales - The Wolf and Seven Kids. The code:
             "overwrite=True,
              learning_rate=1e-5,
              dataset=file_name,
              model_name='124M',
              steps=500,
              restore_from='latest',
              run_name='run1',
              print_every=10,
              sample_every=200,
              save_every=500"
I continue the training on the existed trained model and data (The Potato & The Dragon story).
7. Trained GPT-2 Model with the Potato & Dragon story again. The code:
             "overwrite=True,
              learning_rate=1e-5,
              dataset=file_name,
              model_name='124M',
              steps=200,
              restore_from='latest',
              run_name='run1',
              print_every=10,
              sample_every=200,
              save_every=200"
8. Now the trained model is ready to generate a text. I set the length of the generate text is 3000, and the temperature is 0.7 (which is more crazier), with the prefix "Potato and Dragon".
9. Now I have a kind of crazy-generated text. But I think I trained the Potato & Dragon story too many steps, so the result didn't come out as crazy as I thought. It needs more generates. Then Plan B comes out - Using Tracery to upgrade the text - generation.
10. I actually tried to use Chat GPT to give me a Tracery Grammer Source based on the generated story I gave. But it seems 3000 words is a bit hard for it. So I choose another way to use Tracery.
11. I separete the text into different sections. And then put these sections into OPENAI Playground with the input "write the sentences in different words but same meaning 2 times." Now I have 1 orginal generated text sentence and 2 same meaning but using different words sentences in a section. Then I used the Tracery Grammer to put these sections together. 
12. I also created the HTML, CSS and Java Script as p5.js sketch for user to generate the story. When user press the "Click to generate" button, a random generated story will show up.

## Conclusion
I feel like this project is really interesting to do and also drags me crazy at the same time. I feel like uncontrollable of the generated text is definitely the biggest challenge I'm facing. It's hard to get what I wish to get. So I have to change my plan in the middle of the process. Giving a frame to the generated text is not easy at all.
