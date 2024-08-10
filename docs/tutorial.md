# Assignment Tutorial

## Text Generation

### Dialogue generation with LLMs

In this exercise, our goal is to get familiar with basic LLM prompting, compare different available models, 
explore the limitations of LLMs, as well as to generate entertaining stories and communication scenarios 
for the final demo.

To get familiar with the basics of prompt engineering, we recommend you follow this short course: 
https://learn.deeplearning.ai/login?redirect_course=chatgpt-prompt-eng

You can also refer to this tutorial for a basic introduction/overview: https://www.promptingguide.ai/
You can use ChatGPT, Bard, or any of the LLMs available here Chat with Open Large Language Models 
https://chat.lmsys.org/ to generate text in this assignment. You can also compare different models’ subjective 
performance.

### Creating a story

First, let us start with creating a plot, or a context, for your demo. You can use well-known topics of 
general interest such as articles on scientific subjects, news, etc, to create a story based on it by 
referring the model to sources of knowledge. You can also explore the models’ “reasoning” capabilities 
through chain-of-thought prompting to derive conclusions based on the provided context. You can then 
explore factual correctness of the generated text by asking the model to compare it to other publicly 
available knowledge sources that you originally did not provide. Through iterative prompting, you can 
collaborate with the model on writing the story.

### Introducing characters and creating a dialogue

Now that we have set up the basic story, you can introduce different characters and speech styles by 
describing your characters and their demeanor in the prompts and referring to the story you created as 
the context to turn it into a dialogue. You can, for example, refer to well-known fictional movie 
characters or public figures to make the model mimic their style, or create your own characters by giving 
examples using few-shot prompting.

### Exploring the limitations of LLMs

Some main challenges around using LLMs today include possible biases, unethical and inappropriate 
responses, and factual incorrectness. In particular, while ChatGPT has powerful guardrails making it
avoid giving illegal and unethical responses, with some prompt engineering it is still possible to bypass 
them. Explore the limitations to get a better idea of the current limitations (and possibly a more creative 
demo)

## Speech Generation

Use the model you trained during the summer school pre-assignment to generate speech audio. Use the various models within your team to generate audio with different voices.

The instructions to generate audio are in your Python notebooks on *Canvas*.

## Gesture Generation

We'll use web servers hosted by WASP to generate gestures. If you're interested in a more advanced approach, a command line interface method is available and [documented here](https://github.com/TeoNikolov/wasp-ss-gesgen/blob/main/tutorial.md#approach-b---docker-cli), but it won’t be covered in this tutorial. If you prefer to set up your own web server (e.g., if the WASP servers are unavailable or you want to explore the system in more detail), follow the "Local setup" instructions in the [gesgen repository](https://github.com/TeoNikolov/wasp-ss2023-gesgen/).

!!! Servers
    
    - Server 1 : [http://129.192.83.172](http://129.192.83.172) or [http://wasp1.teonikolov.com](http://wasp1.teonikolov.com)
    - Server 2 : [http://129.192.82.245](http://129.192.82.245) or [http://wasp2.teonikolov.com](http://wasp2.teonikolov.com)

### Task 1. Generate BVH motion from audio

Your first task is to use the ZeroEGGS AI model to create gestures from audio files, which could be synthetic, your voice, or any online audio. Consider the following:

- How does adjusting a parameter impact the animation? Keep the seed constant.
- Does changing the seed produce distinctly different gestures?
- Evaluate the quality and timing of the gestures - can they be improved?

!!! Steps
    	
    1. Access the server web page.
    1. Upload a WAV audio file.
    1. Choose a starting pose and animation style. The starting pose will be used as the first frame of your animation. Pose previews are shown [here](https://github.com/TeoNikolov/wasp-ss-gesgen/tree/main/data/start_poses/images).
    1. Adjust the temperature for gesture variation. Higher values will result in animations that adhere more strongly to the chosen style.
    1. Set a seed. Different seeds will randomize the result.
    1. Click "Download (BVH)" to generate and save the BVH file.

### Task 2. Preview the generated motion

This task involves previewing the animations you generated. With the web-based solution, this is straightforward. Be patient, as creating the preview video might take some time.

!!! Steps
    
    1. Access the server web page.
    1. Upload the generated BVH motion file and its corresponding WAV audio file.
    1. Click "Download (MP4)" to create and save the preview video.

### Task 3. Export the motion as FBX

The final task is to convert the BVH motion file to FBX format, which is required for use in Unreal Engine. You'll use the BVH file generated earlier in this step.

!!! Steps
    
    1. Access the server web page.
    1. Upload the generated BVH motion file.
    1. Click "Download (FBX)" to convert and save the file in FBX format.

## Final notes

If you finished the tutorial, you are free to continue experimenting or do something else! For inspiration, you could:

- Create new audio files and generate new animations
- Experiment with the gesture generation parameters
- Work on systems you used previously during the summer school
- Work on the student assignment for Thursday
- Set up the Docker solution locally, if you have not done so already
- Browse the code to learn more about how various tools were used to create a functioning web app: `FastAPI`, the `Celery` task queue, `Redis`, `Docker` (`Dockerfile`, `docker compose`), the `GENEA Visualiser`, `HTML`, `CSS`, `Javascript` . Feel free to ask questions!
- Install Blender on your computer and inspect the downloaded BVH and FBX files
- Help other teams out
- Have a relaxing discussion with ChatGPT about the essence of life and the universe

Hopefully you had fun and learned something new :)

