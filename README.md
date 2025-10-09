"""
GitHub Repository Simulator
---------------------------
This program simulates basic operations of a GitHub repository.
You can:
- create a repositorY
- add files
- remove files
- list all files
- update repository description
- search for a file
"""

class Repository:
    def __init__(self, name, description, language="Python"):
        self.name = name
        self.description = description
        self.language = language
        self.files = []

    def add_file(self, filename):
        if filename not in self.files:
            self.files.append(filename)
            print(f"✅ File '{filename}' added.")
        else:
            print(f"⚠️ File '{filename}' already exists.")

    def remove_file(self, filename):
        if filename in self.files:
            self.files.remove(filename)
            print(f"🗑 File '{filename}' removed.")
        else:
            print(f"❌ File '{filename}' not found.")

    def show_files(self):
        if self.files:
            print("📂 Repository files:")
            for f in self.files:
                print("   -", f)
        else:
            print("📂 No files in this repository.")

    def update_description(self, new_desc):
        self.description = new_desc
        print("📝 Repository description updated!")

    def search_file(self, filename):
        if filename in self.files:
            print(f"🔍 File '{filename}' found in repository.")
        else:
            print(f"❌ File '{filename}' not found.")

    def show_info(self):
        print("="*50)
        print(f"📦 Repository: {self.name}")
        print(f"📝 Description: {self.description}")
        print(f"💻 Language: {self.language}")
        print(f"📂 Total files: {len(self.files)}")
        print("="*50)


def main():
    print("🚀 Welcome to GitHub Repository Simulator 🚀")

    # Create repository
    repo = Repository(
        name="my-coding-repo",
        description="A simple GitHub-like repository simulator."
    )

    # Show initial info
    repo.show_info()

    # Add files
    repo.add_file("hello.py")
    repo.add_file("README.md")
    repo.add_file("calculator.py")
    repo.add_file("data.json")
    repo.show_files()

    # Remove a file
    repo.remove_file("README.md")
    repo.show_files()

    # Search for files
    repo.search_file("calculator.py")
    repo.search_file("not_exist.py")

    # Update description
    repo.update_description("This repo contains beginner-friendly Python scripts.")
    repo.show_info()


if __name__ == "__main__":
    main()
