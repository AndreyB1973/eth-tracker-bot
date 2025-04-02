# eth-tracker-bot
Telegram bot for ETH whale alerts# Считываем содержимое всех файлов в репозитории eth-tracker-bot
import os

repo_path = "/mnt/data/eth-tracker-bot"
file_contents = {}

for root, dirs, files in os.walk(repo_path):
    for file in files:
        file_path = os.path.join(root, file)
        with open(file_path, "r", encoding="utf-8", errors="ignore") as f:
            relative_path = os.path.relpath(file_path, repo_path)
            file_contents[relative_path] = f.read()

file_contents.keys()  # Показываем, какие файлы найдены
