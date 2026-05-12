# claude-code-partner-certification
## Introduction agent skills
* What are skills?
  - Personal skills go in ~/.claude/skills (your home directory). 
  - Project skills go in .claude/skills inside the root directory of your repository.
  - CLAUDE.md files load into every conversation.
  - Skills load on demand when they match your request.
  - Slash commands require you to explicitly type them.
  - The rule of thumb is simple: if you find yourself explaining the same thing to Claude repeatedly, that's a skill waiting to be written.
  
* Creating your first skill
  - A skill is a directory containing a SKILL.md file with metadata (name, description) in frontmatter and instructions below.
  - Claude loads only skill names and descriptions at startup, then matches incoming requests against those descriptions using semantic matching
  - 쿼리와 semantic matching 되는 description 을 찾으면 You get a confirmation prompt before Claude loads the full skill content into context
  - name conflicts에 대한 priority는 : **Enterprise → Personal → Project → Plugins**
  - To update a skill, edit its SKILL.md. To remove one, delete its directory. **Always restart** Claude Code for changes to take effect
     - 만들기 예제
         - ~/.claude/skills/pr-description 디렉토리를 만들고, SKILL.md 파일을 해당 디렉토리 밑에 추가하고,
         - SKILL.md 파일은 *---* 3개 dash로 시작, 끝나는 frontmatter dash 가 있고, 해당 dash 내에는 디렉토리명과 일치하는 name: 과 description: 2개 문장을 넣는다.
         - frontmatter 이후는 skill 로드 이후 çlaude가 따라야 하는 명령어를 적는다.

* Configuration and multi-file skills
* Skills vs. other Claude Code features
* Sharing skills
* Troubleshooting skills
