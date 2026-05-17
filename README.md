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
  - description을 잘 써야 하고, 좋은 description은 아래 2개 질문에 대한 명확한 답을 정리해서 적는 것임(뭐 하는 스킬인지, 언제 클로드가 쓰면 되는지)
     - What does the skill do?
     - When should Claude use it?
  - allowed-tools : default 는 모든 툴을 사용하는 것이고, 한정시켜야만 특정툴만 사용한다.
  - progressive disclosure : 500줄을 넘기면 별도 reference 파일들로 구성해라.
     - The open standard suggests organizing your skill directory with:
     - scripts/ — Executable code
     - references/ — Additional documentation
     - assets/ — Images, templates, or other data files
   
  - Using script : The key instruction to include in your SKILL.md is to tell Claude to **run the script, not read** it.

* What does the skill do?
  - 스킬, claude.md, sub-sgent, hook, mcp가 있음
  - 각각 호출되는 방식이 다름. 
* Sharing skills
  - git repository로 배포 가능
  - plugin marketplace 배포 가능
  - enterprise setting 으로 가능
    
* Troubleshooting skills
  - SKILL.md 파일에 잘 작성되어 있어야 하고, 실행모드, 엔ㅌㅓ프라이즈 등 상위 권한, description 충돌 등을 피해야 한다.
