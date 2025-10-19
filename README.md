# Claude Skills Archive

This repository serves as an archive and reference collection of specialized Claude Skills designed to enhance Claude's capabilities in specific domains. These skills provide structured methodologies, detailed workflows, and best practices that can be loaded into Claude conversations to enable advanced functionality.

## What are Claude Skills?

Claude Skills are specialized instruction sets that extend Claude's capabilities by providing:

- **Domain Expertise**: Focused knowledge and methodologies for specific areas
- **Structured Workflows**: Step-by-step processes and patterns for complex tasks
- **Quality Standards**: Best practices and validation criteria
- **Concrete Examples**: Practical demonstrations and templates
- **Role Definitions**: Clear guidance on how to approach domain-specific challenges

Each skill is packaged as a markdown document containing comprehensive instructions that transform Claude into a specialized assistant for particular use cases.

## How to Use Claude Skills

### Loading a Skill

1. Navigate to the desired skill directory (e.g., `TINS/` or `Unfold/`)
2. Open the skill file (`skill.md` or `SKILL.md`)
3. Copy the entire contents of the skill file
4. In your Claude conversation, paste the skill content as a message
5. Claude will acknowledge the skill and operate according to its specifications

### When to Use Skills

- **TINS**: When creating comprehensive README-first documentation or generating implementations from detailed specifications
- **Unfold**: When managing complex development projects that need to be broken into manageable, documented phases

### Integration

Skills work seamlessly with Claude's existing capabilities. Once loaded, Claude will:
- Apply the skill's methodology to your requests
- Follow the skill's quality standards
- Use the skill's terminology and patterns
- Provide outputs according to the skill's specifications

You can switch between skills in the same conversation or use multiple skills sequentially as needed.

## Available Skills

### TINS (There Is No Source)

**Purpose**: Creating TINS-compliant README files, generating implementations from TINS READMEs, and validating TINS documentation

**Key Capabilities**:
- Generate comprehensive, implementation-ready README files
- Create complete code implementations from README specifications
- Validate documentation for completeness and clarity
- Enhance existing TINS documentation

**License**: See TINS/LICENSE.txt

**Location**: `TINS/skill.md`

---

### Unfold

**Purpose**: Stage-based planning methodology for breaking complex development plans into manageable phase and substage documents with detailed step-by-step instructions

**Key Capabilities**:
- Transform high-level plans into sequential phase documents
- Break complex phases into detailed substage instructions
- Generate complete code examples and implementation guides
- Maintain document hierarchy with character limits (< 45,000 chars per document)

**License**: MIT

**Location**: `Unfold/SKILL.md`

---

## Skill Structure

Each skill follows a consistent structure:

```markdown
---
name: skill-name
description: Brief description
license: License type
---

# Skill Title

## Role and Purpose
[Core definition and objectives]

## Core Capabilities
[Main features and functions]

## Best Practices
[Guidelines and standards]

## Examples
[Concrete usage patterns]

## Additional Sections
[Skill-specific content]
```

## Contributing

This archive is designed to preserve and share useful Claude Skills. If you have additional skills to contribute or improvements to existing ones, please ensure they:

- Follow the established skill structure
- Include comprehensive documentation
- Provide concrete examples
- Specify clear use cases
- Include appropriate licensing information

## 📚 Citation

### Academic Citation

If you use this codebase in your research or project, please cite:

```bibtex
@software{djz_claude_skills,
  title = {DJZ Claude Skills: Collection of Skill.md files for Claude},
  author = {[Drift Johnson]},
  year = {2025},
  url = {https://github.com/MushroomFleet/DJZ-Claude-Skills},
  version = {1.0.0}
}
```



**Repository Purpose**: Archive and reference collection for specialized Claude Skills

**Last Updated**: 2025-10-18

**Note**: Skills are provided as-is for educational and practical use. Ensure you understand each skill's methodology before applying it to production work.

