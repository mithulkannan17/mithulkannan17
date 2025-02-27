from PIL import Image, ImageDraw, ImageFont

def create_github_profile_image(text_lines, output_path="github_profile.png", image_width=800, image_height=400):
    """
    Creates an image for a GitHub profile, with a clean and professional style.

    Args:
        text_lines (list): A list of strings, each string representing a line of text.
        output_path (str): The file path where the generated image will be saved.
        image_width (int): The width of the image.
        image_height (int): The height of the image.
    """

    background_color = (255, 255, 255)  # White background
    text_color = (0, 0, 0)  # Black text

    image = Image.new("RGB", (image_width, image_height), background_color)
    draw = ImageDraw.Draw(image)

    # Font settings (adjust to your preference)
    try:
        header_font = ImageFont.truetype("arial.ttf", 60)  # Adjust font size
        main_font = ImageFont.truetype("arial.ttf", 30)  # Adjust font size
    except IOError:
        print("Font not found. Using default font.")
        header_font = ImageFont.load_default()
        main_font = ImageFont.load_default()

    y_position = 50  # Starting Y position (adjust for vertical centering)
    x_position = 50  # Starting X position (adjust for horizontal centering)

    # Header (your name or title)
    header_text = text_lines[0].strip()
    header_width, header_height = draw.textsize(header_text, font=header_font)
    draw.text((x_position, y_position), header_text, font=header_font, fill=text_color)

    y_position += header_height + 20  # Space after header

    # Main text (your description)
    for line in text_lines[1:]:
        line = line.strip()
        text_width, text_height = draw.textsize(line, font=main_font)
        draw.text((x_position + 10, y_position), line, font=main_font, fill=text_color)
        y_position += text_height + 10  # Space between lines

    image.save(output_path)
    print(f"GitHub profile image saved to {output_path}")

# Example usage (customize your text)
profile_text = [
    "Elizaveta", # Your name or main title
    "Aspiring Data Scientist",
    "Passionate about problem-solving",
    "Driven by innovation and creativity"
]

create_github_profile_image(profile_text)


- 👋 Hi, I’m @mithulkannan17
- 👀 I’m interested in software development, particularly in Python and web development. I also enjoy exploring machine learning concepts.
- 🌱 I’m currently learning advanced Python techniques and diving deeper into React.js.
- 💞️ I’m looking to collaborate on open-source projects related to web development or small Python utilities.
- 📫 How to reach me: You can reach me via email at mithulkannan17@example.com (replace with your actual email) or through direct messages on GitHub.
- 😄 Pronouns: He/Him
- ⚡ Fun fact: I enjoy playing games and solving puzzles in my free time.

<!---
mithulkannan17/mithulkannan17 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
