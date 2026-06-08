#!/usr/bin/env python3
import sys, anthropic

if len(sys.argv) < 3 or sys.argv[1] != "-p":
    print("Usage: claude -p <file>")
    sys.exit(1)

file_path = sys.argv[2]
with open(file_path) as f:
    content = f.read()

client = anthropic.Anthropic()
response = client.messages.create(
    model="claude-3-opus-20240229",
    max_tokens=500,
    messages=[{"role": "user", "content": content}]
)
print(response.content[0].text)
