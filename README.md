# Ex.No.9 Exploration of Prompting Techniques for Video Generation

# Date: 19/05/2025
# Reg. No.: 212222060185

## Aim:
To demonstrate the ability of text-to-Video generation tools to reproduce an existing Video by crafting precise prompts. The goal is to identify key elements within the Video and use these details to generate an Video as close as possible to the original.

## Software Requirements
1. Python 3.8+ and an IDE (e.g., Jupyter, VS Code).
2. Libraries:
o requests for API interaction.
o moviepy for video editing (optional for enhancing or combining outputs).
3. APIs and Tools:
o RunwayML or DeepMotion for animation generation. 
o Hugging Face (Stable Diffusion for image/video models).
 o OpenAI GPT for narrative and prompt
refinement.
o Synthesia.io or Pictory for creating AI-generated videos with text-to-video tools.

## Experiment Design
## Experiment 1: Generating Animated Scenes
• Objective: Use different prompt styles to generate short animations based on scene descriptions.
• Prompts:
o Basic: "Generate a cartoon of a cat chasing a mouse."
o Detailed: "Create a 2D animation of a playful orange tabby cat chasing a gray mouse in a sunny green field."
o Contextual: "Produce an animation where a cat and mouse chase each other through a vibrant forest during autumn."

## Code: python
```
Copy code
import requests

def generate_animation(prompt): API_KEY =
"your_runwayml_api_key" url =
"https://api.runwayml.com/v1/videos" headers =
{"Authorization": f"Bearer {API_KEY}"} payload =
{"text_prompt": prompt, "model": "animation"} response =
requests.post(url, headers=headers, json=payload) if
response.status_code == 200:
print("Generated animation URL:", response.json().get("video_url"))
else:
print("Error:", response.json())
# Example usage generate_animation("Create an animation of a robot
exploring Mars.")
```
## Experiment 2: Generating Video Summaries
• Objective: Explore how prompt specificity affects the generation of video summaries from text or long videos.
• Prompts:
o Simple: "Summarize a video about AI applications."
o Detailed: "Generate a 2-minute video summarizing AI's use in healthcare, focusing on diagnosis and treatment."
o Contextual: "Create a video summary of a 10-minute lecture on climate change, highlighting solutions for reducing carbon emissions."

## Code: python 
```
Copy code 
def generate_video_summary(text_prompt):
API_KEY = "your_huggingface_api_key" url = "https://api-
inference.huggingface.co/models/video-summary-model" headers =
{"Authorization": f"Bearer {API_KEY}"} payload = {"inputs":
text_prompt} response = requests.post(url, headers=headers, json=payload)
if response.status_code == 200:
print("Generated video summary:", response.json().get("video_url"))
else:
print("Error:", response.json())
# Example usage generate_video_summary("Create a video summarizing AI in
autonomous vehicles.")
```

## Experiment 3: Enhancing Video Content with Visual Effects
• Objective: Test how descriptive prompts influence the generation of visual effects for existing videos.
• Prompts:
o Basic: "Add fireworks to this video."
o Detailed: "Overlay realistic fireworks in the night sky during the final scene of this video."
 o Contextual: "Add vibrant, sparkling fireworks over the Eiffel Tower at midnight."
 
## Code: python 
```
Copy code
import moviepy.editor as mp
def
add_effects_to_video(video_
path, output_path):
# Placeholder for actual AI effects logic print(f"Adding effects to
{video_path}. Output will be saved to {output_path}.")
# Example usage add_effects_to_video("input_video.mp4",
"output_with_effects.mp4")
For actual AI-based enhancements, integrate with video-effect models like RunwayML or DeepMotion.
```

## Output and Results
1. Animated Scenes:
o Basic prompts produce generic animations.
o Detailed prompts create engaging, visually rich content.
2. Video Summaries: o Contextual prompts lead to summaries with better focus and flow.
3. Visual Effects:
o Adding detailed prompts improves the realism and integration of effects

## Conclusion:
By using detailed and well-crafted prompts, text-to-Video generation models can be effective in reproducing an Video closely. The quality of the generated Video depends on how accurately the prompt describes the Video's key elements. The experiment demonstrates the importance of prompt refinement and iteration when working with AI tools to achieve desired outcomes. With practice, the model can generate Videos that closely match real-world visuals, which is useful for creative and practical applications.
