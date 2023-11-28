def justify_paragraph(paragraph, page_width):
    words = paragraph.split()
    lines = []
    current_line = []

    for word in words:
        if len(' '.join(current_line + [word])) <= page_width:
            current_line.append(word)
        else:
            lines.append(current_line)
            current_line = [word]

    if current_line:
        lines.append(current_line)

    justified_lines = []
    for line in lines:
        spaces_to_add = page_width - sum(len(word) for word in line)
        num_words = len(line)

        if num_words == 1:
            justified_line = line[0] + ' ' * spaces_to_add
        else:
            spaces_between_words = spaces_to_add // (num_words - 1)
            extra_spaces = spaces_to_add % (num_words - 1)
            justified_line = (' ' * spaces_between_words).join(
                [word + ' ' for word in line[:-1]]) + line[-1] + ' ' * extra_spaces

        justified_lines.append(justified_line)

    return justified_lines

def main():
    paragraph = "This is a sample text but a complicated problem to be solved, so we are adding more text to see that it actually works."
    page_width = 20

    justified_array = justify_paragraph(paragraph, page_width)

    for i, line in enumerate(justified_array, 1):
        print(f"Array [{i}] = \"{line}\"")

if __name__ == "__main__":
    main()
