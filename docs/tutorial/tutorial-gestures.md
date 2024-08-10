# Gesture Generation Tutorial
In this tutorial you will:
- Generate BVH motion from WAV audio using AI (ZeroEGGS)
- Preview the generated motion as a MP4 video
- Export the generated BVH motion as an FBX file

We'll use web servers hosted by WASP to complete these tasks. If you're interested in a more advanced approach, a command line interface method is available and [documented here](https://github.com/TeoNikolov/wasp-ss-gesgen/blob/main/tutorial.md#approach-b---docker-cli), but it won’t be covered in this tutorial.

---

WASP provides two web servers:
- Server 1 (recommended) : [http://129.192.83.172](http://129.192.83.172) or [http://wasp.teonikolov.com](http://wasp.teonikolov.com)
- Server 2 : [http://129.192.82.245](http://129.192.82.245) or [http://wasp2.teonikolov.com](http://wasp2.teonikolov.com)

If you prefer to set up the server on your own machine (e.g., if the WASP servers are unavailable or you want to explore the system in more detail), follow the "Local setup" instructions in the [gesgen repository](https://github.com/TeoNikolov/wasp-ss2023-gesgen/).

## Task 1. Generate BVH motion from audio
Your first task is to use the ZeroEGGS AI model to create gestures from audio files, which could be synthetic, your voice, or any online audio. Consider the following:
- How does adjusting a parameter impact the animation? Keep the seed constant.
- Does changing the seed produce distinctly different gestures?
- Evaluate the quality and timing of the gestures - can they be improved?

**Steps**

1. Access the server web page.
2. Upload a WAV audio file.
3. Choose a starting pose and animation style. The starting pose will be used as the first frame of your animation. Pose previews are shown [here](https://github.com/TeoNikolov/wasp-ss-gesgen/tree/main/data/start_poses/images).
4. Adjust the temperature for gesture variation. Higher values will result in animations that adhere more strongly to the chosen style.
5. Set a seed. Different seeds will randomize the result.
6. Click "Download (BVH)" to generate and save the BVH file.

## Task 2. Preview the generated motion
This task involves previewing the animations you generated. With the web-based solution, this is straightforward. Be patient, as creating the preview video might take some time.

**Steps**

1. Upload the generated BVH motion file and its corresponding WAV audio file.
2. Click "Download (MP4)" to create and save the preview video.

## Task 3. Export the motion as FBX
The final task is to convert the BVH motion file to FBX format, which is required for use in Unreal Engine. You'll use the BVH file generated earlier in this step.

**Steps**

1. Upload the generated BVH motion file.
2. Click "Download (FBX)" to convert and save the file in FBX format.

# Final notes
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

