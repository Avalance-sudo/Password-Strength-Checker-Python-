import tkinter as tk
from tkinter import ttk
from tkinter import messagebox
import string

def password_strength(password):
    score = 0
    feedback = []
    length = len(password)
    lower_count = sum(1 for c in password if c.islower())
    upper_count = sum(1 for c in password if c.isupper())
    digit_count = sum(1 for c in password if c.isdigit())
    special_count = sum(1 for c in password if c in string.punctuation)

    if length >= 8:
        score += 1
    else:
        feedback.append("Make your password longer (at least 8 characters).")
    if length > 12:
        score += 1
    if upper_count > 0:
        score += 1
    else:
        feedback.append("Include at least one uppercase letter.")
    if lower_count > 0:
        score += 1
    else:
        feedback.append("Include at least one lowercase letter.")
    if digit_count > 0:
        score += 1
    else:
        feedback.append("Add at least one digit.")
    if special_count > 0:
        score += 1
    else:
        feedback.append("Add at least one special character.")

    if score >= 5:
        strength = "Strong"
    elif score >= 3:
        strength = "Medium"
    else:
        strength = "Weak"

    return score, strength, feedback


def gui_password_checker():
    def apply_theme(score):
        if score <= 2:
            # Gothic pixel hell aesthetic
            root.configure(bg="#1a1a1a")
            canvas.configure(bg="#1a1a1a")
            canvas.delete("all")
            canvas.create_text(250, 60, text="⚠️ DANGER ZONE ⚠️", fill="#ff3b3b", font=("Press Start 2P", 12))
            canvas.create_text(250, 100, text="LOW SECURITY", fill="#ff6ec7", font=("Press Start 2P", 10))
        elif score <= 4:
            # Neutral theme
            root.configure(bg="#2a2a44")
            canvas.configure(bg="#2a2a44")
            canvas.delete("all")
            canvas.create_text(250, 60, text="City Under Construction", fill="#facbff", font=("Press Start 2P", 10))
        else:
            # Pixel city sunset vibes
            root.configure(bg="#ffaec9")
            canvas.configure(bg="#ffaec9")
            canvas.delete("all")
            canvas.create_text(250, 60, text="✨ Welcome to Pixel City ✨", fill="#6c3ba6", font=("Press Start 2P", 12))
            canvas.create_text(250, 100, text="High Security Zone", fill="#ffffff", font=("Press Start 2P", 10))

    def check_password_gui():
        password = entry.get()
        score, strength, feedback = password_strength(password)
        result_label.config(text=f"Password Strength: {strength} (Score: {score}/6)")
        feedback_text.delete(1.0, tk.END)

        apply_theme(score)

        if feedback:
            feedback_text.insert(tk.END, "\n".join(feedback))
        else:
            feedback_text.insert(tk.END, "✨ Perfect! Your password is rock solid! ✨")

    root = tk.Tk()
    root.title("Pixel City Password Strength Checker")
    root.geometry("520x400")
    root.resizable(False, False)

    # Bring window to front and focus
    root.lift()
    root.attributes('-topmost', True)
    root.after_idle(root.attributes, '-topmost', False)
    root.focus_force()

    # Optional: set window icon (uncomment and provide path to .ico file)
    # root.iconbitmap("your_icon.ico")

    # Show welcome message box when app starts
    root.after(100, lambda: messagebox.showinfo("Welcome", "Welcome to Pixel City Password Strength Checker!"))

    # Fonts and colors
    font_main = ("Courier New", 11, "bold")
    font_pixel = ("Press Start 2P", 9)  # Install this font for full pixel aesthetic
    color_text = "#D8B4F2"  # Light purple for text
    color_input_bg = "#6C3BA6"
    color_feedback = "#1E1E1E" # Dark gray for feedback text

    # Style
    style = ttk.Style()
    style.theme_use('clam')
    style.configure("TLabel", background="#000", foreground=color_text, font=font_main)
    style.configure("TButton", background="#FF69B4", foreground="#000", font=font_main)
    style.configure("TEntry", fieldbackground=color_input_bg, foreground=color_text)

    # Canvas for pixel visual change
    canvas = tk.Canvas(root, width=500, height=130, bg="#000000", highlightthickness=0)
    canvas.pack(pady=10)

    ttk.Label(root, text="Enter your password:").pack(pady=5)
    entry = ttk.Entry(root, show='*', width=30)
    entry.pack(pady=5)

    check_button = ttk.Button(root, text="Check Password", command=check_password_gui)
    check_button.pack(pady=10)

    result_label = ttk.Label(root, text="")
    result_label.pack(pady=5)

    feedback_text = tk.Text(root, height=6, width=55, bg="#1a1a1a", fg=color_feedback, font=font_main)
    feedback_text.pack(pady=5)

    root.mainloop()


if __name__ == "__main__":
    gui_password_checker()
