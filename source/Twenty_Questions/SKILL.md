---
name: Twenty_Questions
description: Structured interview methodology for collecting comprehensive information through dynamic, context-aware questioning with progressive artifact updates
license: MIT
---

# Twenty Questions Interview Skill

## Overview

The Twenty Questions skill provides a systematic methodology for conducting focused, in-depth interviews through a series of 20 dynamically-generated questions. Each question builds upon previous responses, and all Q&A pairs are progressively captured in a continuously-updated markdown artifact. This creates a comprehensive knowledge document that evolves throughout the conversation.

## Core Concepts

### Progressive Artifact Building
- A markdown artifact is created at the start of the interview, named after the topic/task
- After each question is answered, the artifact is immediately updated with the Q&A pair
- The artifact serves as both a running transcript and a structured knowledge base
- Upon completion, the artifact contains the full interview with all 20 Q&A pairs

### Dynamic Question Generation
- Questions are not pre-scripted but generated adaptively based on:
  - Previous answers provided by the interviewee
  - Context from any attached or referenced materials
  - The overall topic/goal of the interview
  - Gaps in understanding that need to be filled
  - Natural conversation flow and relevance

### Context Integration
- Initial input data (attachments, references, descriptions) establishes the interview focus
- Each subsequent question considers all prior context
- Questions probe deeper into areas that need clarification or expansion
- The interview maintains coherent thematic unity throughout

## Interview Process

### Stage 1: Initialization

**When the interview begins:**

1. **Identify the Topic**
   - Extract the topic/subject from the user's initial prompt
   - If unclear, ask for clarification about the interview focus
   - Determine the primary goal: information gathering, planning, analysis, etc.

2. **Process Input Data**
   - If user provides attachments (documents, images, etc.), review them thoroughly
   - If user references materials, incorporate that context
   - If user provides a detailed description, use it as foundation

3. **Create Initial Artifact**
   - Name format: `[Topic]_Interview.md` or `[Project]_20Questions.md`
   - Include header with topic, date/time, and purpose
   - Create structure for Q&A pairs
   - Add introduction explaining the interview's focus

**Initial Artifact Template:**
```markdown
# [Topic Name] - Twenty Questions Interview

**Date:** [Current Date]
**Purpose:** [Brief description of interview goal]
**Focus:** [Main areas to be covered]

---

## Introduction

This interview explores [topic] through 20 structured questions designed to capture comprehensive information about [specific areas of focus].

---

## Interview Questions & Responses

[Q&A pairs will be added progressively]

---

## Summary

[To be completed after all 20 questions]
```

### Stage 2: Question Generation & Response Cycle

**For each question (1-20):**

1. **Generate Next Question**
   - Consider all previous answers
   - Identify gaps or areas needing elaboration
   - Ensure question adds new valuable information
   - Maintain natural conversation flow
   - Adapt complexity and depth based on user's responses
   - Avoid redundancy with previous questions

2. **Question Formulation Guidelines**
   - Make questions clear and specific
   - Avoid yes/no questions when more detail would be valuable
   - Use open-ended phrasing to encourage detailed responses
   - Build on specific details from previous answers
   - Target different aspects of the topic across questions

3. **Present Question**
   - State the question number (e.g., "Question 7 of 20:")
   - Ask one question at a time
   - Provide context if needed to frame the question
   - Wait for user's response before proceeding

4. **Process Response**
   - Carefully read and understand the user's answer
   - Extract key information and insights
   - Identify areas that might need follow-up in future questions
   - Note any new topics or angles that emerged

5. **Update Artifact**
   - Immediately append the Q&A pair to the artifact
   - Maintain consistent formatting
   - Ensure clean, readable structure
   - Keep running question count visible

**Q&A Format in Artifact:**
```markdown
### Question [N] of 20

**Q:** [Full question text]

**A:** [Complete user response]

---
```

### Stage 3: Interview Progression

**Early Questions (1-7):**
- Establish foundational understanding
- Cover core aspects of the topic
- Build broad context
- Identify key themes and priorities

**Middle Questions (8-14):**
- Dive deeper into specific areas
- Explore nuances and details
- Address complexities and challenges
- Follow interesting threads from early responses

**Late Questions (15-20):**
- Fill remaining gaps
- Probe edge cases or special considerations
- Clarify ambiguities from earlier responses
- Capture final critical details
- Look toward implications and next steps

### Stage 4: Completion

**After Question 20:**

1. **Thank the User**
   - Acknowledge their time and detailed responses
   - Highlight particularly valuable insights shared

2. **Generate Summary**
   - Synthesize key findings from all 20 responses
   - Identify major themes and patterns
   - Highlight critical information discovered
   - Note any areas that could benefit from further exploration

3. **Update Final Artifact**
   - Add comprehensive summary section
   - Include key takeaways (bullet points)
   - Add any relevant next steps or recommendations
   - Ensure document is polished and complete

4. **Present Final Artifact**
   - Provide the complete interview document
   - Offer to clarify or expand on any specific sections
   - Suggest potential follow-up actions if appropriate

**Final Summary Template:**
```markdown
## Summary

### Key Findings

[Narrative summary of the most important information gathered]

### Major Themes

1. **[Theme 1]:** [Brief description]
2. **[Theme 2]:** [Brief description]
3. **[Theme 3]:** [Brief description]

### Critical Insights

- [Insight 1]
- [Insight 2]
- [Insight 3]

### Recommendations / Next Steps

[Actionable recommendations based on the interview responses]

### Areas for Further Exploration

[Topics that emerged but weren't fully covered, if any]
```

## Question Generation Strategies

### Building on Context

**Good Practice:**
```
Question 5: You mentioned that budget constraints are a primary concern. 
Can you walk me through the specific budget parameters and how they 
impact your timeline choices?
```

**Avoid:**
```
Question 5: What about budget?
```

### Exploring Multiple Dimensions

For a project planning interview, cover:
- Goals and objectives
- Constraints and limitations
- Resources and requirements
- Timeline and milestones
- Stakeholders and decision-makers
- Success criteria
- Risks and challenges
- Dependencies
- Technical requirements
- User/customer needs

### Probing Techniques

1. **Clarification:** "Could you elaborate on what you meant by [specific term]?"
2. **Depth:** "What factors led you to that conclusion?"
3. **Breadth:** "Are there other aspects of [topic] we should consider?"
4. **Specificity:** "Can you provide a concrete example of [concept]?"
5. **Comparison:** "How does [X] compare to [Y] in your situation?"
6. **Future-oriented:** "How do you see [aspect] evolving over time?"
7. **Challenge-focused:** "What obstacles do you anticipate with [element]?"

## Best Practices

### Interview Facilitation

1. **Maintain Focus**
   - Keep questions aligned with the interview's purpose
   - Avoid tangents that don't add value
   - Redirect gently if responses drift off-topic

2. **Be Adaptive**
   - Adjust question difficulty based on user's expertise level
   - Follow unexpected but valuable threads
   - Skip redundant areas if already covered thoroughly

3. **Show Understanding**
   - Acknowledge key points in responses
   - Demonstrate listening by referencing earlier answers
   - Build rapport through engaged questioning

4. **Balance Depth and Breadth**
   - Don't spend all 20 questions on one narrow area
   - Don't skim over complex topics that need exploration
   - Allocate questions proportionally to importance

### Artifact Management

1. **Update Immediately**
   - Never skip updating the artifact after a response
   - Maintain version control through continuous updates
   - Ensure each update is clean and error-free

2. **Format Consistently**
   - Use identical formatting for all Q&A pairs
   - Keep numbering sequential and clear
   - Maintain proper markdown structure

3. **Preserve Fidelity**
   - Capture responses accurately
   - Don't paraphrase unless necessary for clarity
   - Include relevant details even if lengthy

### Quality Control

1. **Avoid Redundancy**
   - Track what's been asked to prevent repetition
   - Reference previous answers rather than re-asking
   - Synthesize related information across questions

2. **Ensure Coverage**
   - Monitor which aspects have been addressed
   - Identify gaps as the interview progresses
   - Use final questions to fill critical holes

3. **Maintain Flow**
   - Create natural question sequences
   - Use transitions that connect questions logically
   - Build narrative coherence across the interview

## Example Interview Scenarios

### Scenario 1: Product Development Planning

**Topic:** Mobile app development for fitness tracking

**Sample Question Progression:**
- Q1: What is the primary goal you want to achieve with this fitness tracking app?
- Q2: Who is your target user demographic, and what specific needs do they have?
- Q3: What existing fitness apps have you evaluated, and what gaps did you identify?
- Q4: Can you describe the core features you envision for the initial release?
- Q8: You mentioned integration with wearable devices—which platforms are priorities?
- Q12: How do you plan to differentiate your app from established competitors like MyFitnessPal?
- Q16: What technical stack are you considering, and what guided those choices?
- Q20: Looking 6-12 months post-launch, what success metrics will matter most?

### Scenario 2: User Research Interview

**Topic:** Understanding customer pain points with e-commerce checkout

**Sample Question Progression:**
- Q1: What prompted you to examine your checkout process specifically?
- Q2: Can you walk me through the current checkout flow from cart to confirmation?
- Q3: What data or feedback do you have about where users are dropping off?
- Q5: You mentioned cart abandonment is around 70%—at which step do most users exit?
- Q9: What security and payment methods are currently supported?
- Q14: How does your checkout compare to competitors you consider best-in-class?
- Q18: What technical constraints limit potential improvements?
- Q20: If you could change one thing about checkout tomorrow, what would it be?

### Scenario 3: Requirements Gathering

**Topic:** Internal tool for employee onboarding

**Sample Question Progression:**
- Q1: What challenges does your current onboarding process face?
- Q2: How many new employees do you typically onboard per month?
- Q3: Which departments will use this tool, and do they have different needs?
- Q6: What information must new hires receive on day one versus week one?
- Q10: You mentioned compliance training—what specific requirements must be met?
- Q15: How will you measure whether onboarding quality improves?
- Q19: What's your timeline for deploying this tool?
- Q20: Who are the key stakeholders that need to approve this solution?

## Integration with Other Skills

### Combining with Document Creation
- After completing the interview, use docx skill to create a formatted report
- Transform interview transcript into executive summary
- Generate action items document from key findings

### Combining with Planning Skills
- Use interview insights to create project plans
- Feed findings into Unfold skill for detailed phase planning
- Generate specifications based on gathered requirements

### Combining with Analysis
- Analyze patterns across multiple interviews
- Create comparison matrices from parallel interview sets
- Generate insights reports synthesizing findings

## Triggering Twenty Questions

**Claude should initiate this skill when:**
- User explicitly requests "20 questions interview"
- User says "interview me about [topic]"
- User says "collect information about [subject]"
- User requests "structured questions on [theme]"
- Context suggests systematic information gathering is needed

**Indicators for this approach:**
- Complex topic requiring comprehensive understanding
- Need to extract detailed knowledge from user
- Planning or requirements gathering phase
- User wants to think through something systematically
- Situation benefits from guided exploration

## Customization Options

### Adjusting Question Count
While 20 is the default, this can be adjusted:
- **Quick Interview:** 10 questions for focused topics
- **Standard Interview:** 20 questions for comprehensive coverage
- **Extended Interview:** 30 questions for complex, multifaceted subjects

### Interview Styles
Adapt tone and approach:
- **Formal:** Business requirements, compliance, official documentation
- **Conversational:** User research, brainstorming, creative exploration
- **Technical:** System design, architecture planning, technical specs
- **Advisory:** Consulting, recommendations, strategic planning

### Specialized Applications
- **User Personas:** Build detailed user profiles
- **Competitive Analysis:** Systematic competitor evaluation
- **Risk Assessment:** Comprehensive risk identification
- **Retrospectives:** Project post-mortems and lessons learned
- **Stakeholder Interviews:** Requirements from key stakeholders

## Quality Checklist

### Before Starting
- [ ] Interview topic is clearly defined
- [ ] Purpose and scope are understood
- [ ] Initial artifact structure is created
- [ ] Any provided materials have been reviewed

### During Interview
- [ ] Each question builds on previous context
- [ ] Questions avoid redundancy
- [ ] Artifact is updated after each response
- [ ] Formatting remains consistent
- [ ] Natural conversation flow is maintained

### After Completion
- [ ] All 20 questions have been asked and answered
- [ ] Comprehensive summary is generated
- [ ] Key themes are identified
- [ ] Artifact is complete and polished
- [ ] Next steps or recommendations are provided

## Advanced Techniques

### Branching Question Paths
Based on early responses, adapt the interview direction:
```
If Answer 3 indicates technical focus → Questions 4-7 explore technical details
If Answer 3 indicates business focus → Questions 4-7 explore business aspects
```

### Multi-Modal Integration
- Analyze uploaded documents to inform questions
- Reference images or diagrams in questions
- Incorporate data from spreadsheets into interview context

### Follow-Up Mechanics
Within the 20 questions, you can use follow-ups:
- Ask Question 7
- If response reveals new critical area, Question 8 can dive deeper into it
- Use Questions 9-10 to fully explore before moving to new territory

### Meta-Questions
Periodically (e.g., Q10, Q15) check-in:
- "Are we covering the areas most important to you?"
- "Is there a direction you'd like these questions to explore more?"
- "What haven't I asked about that I should?"

## Common Pitfalls to Avoid

1. **Generic Questions:** Don't ask questions that could apply to any topic
2. **Leading Questions:** Avoid questions that suggest a particular answer
3. **Compound Questions:** Ask one thing at a time, not multiple questions at once
4. **Premature Summary:** Don't synthesize conclusions before gathering all data
5. **Ignoring Context:** Always reference and build upon what's been shared
6. **Losing Thread:** Maintain coherent focus throughout the interview
7. **Artifact Neglect:** Never forget to update the artifact after each response

## Output Examples

### Complete Mini-Interview Artifact

```markdown
# Website Redesign Project - Twenty Questions Interview

**Date:** October 18, 2025
**Purpose:** Gather requirements for corporate website redesign
**Focus:** User experience, technical requirements, business goals

---

## Introduction

This interview explores the website redesign project through 20 structured questions designed to capture comprehensive information about project goals, technical requirements, user needs, and business objectives.

---

## Interview Questions & Responses

### Question 1 of 20

**Q:** What is the primary driver for this website redesign—is it user feedback, business goals, technical debt, or something else?

**A:** It's primarily driven by user feedback. We've received consistent complaints about difficulty finding information and slow page load times. Our analytics show high bounce rates on key pages. Additionally, our current site isn't mobile-responsive, which is a major problem since 60% of our traffic is mobile.

---

### Question 2 of 20

**Q:** You mentioned high bounce rates on key pages—which specific pages are most problematic, and what do your analytics tell you about user behavior on those pages?

**A:** Our product catalog pages have 75% bounce rates, and the support/documentation section has 68%. Analytics show users spend less than 30 seconds on these pages before leaving. We suspect the navigation structure makes it hard to drill down into specifics. Also, our search function returns poor results.

---

[Questions 3-19 continue with similar format]

---

### Question 20 of 20

**Q:** As we wrap up, what would you consider the single most important success criterion for this redesign six months after launch?

**A:** Measurable improvement in user task completion rates. Right now, only 40% of users who start the process of finding product documentation actually complete it. I'd want to see that above 75% within six months. That would indicate we've truly solved the usability problems.

---

## Summary

### Key Findings

This website redesign project is driven by significant usability issues identified through user feedback and analytics. The primary problems center around poor mobile experience, difficult navigation, inadequate search functionality, and high bounce rates on critical pages. The project has executive support and a realistic timeline of 6-8 months with a mid-size budget allocated.

### Major Themes

1. **User Experience Problems:** Mobile responsiveness, navigation complexity, search quality
2. **Technical Modernization:** Moving from outdated CMS, improving performance, updating tech stack
3. **Business Impact:** Current site limits customer self-service, increases support costs
4. **Measurable Goals:** Focus on task completion rates and page load times

### Critical Insights

- 60% of traffic is mobile, yet site is not mobile-responsive—urgent priority
- High bounce rates (75% on product pages) indicate fundamental navigation problems
- Search functionality is essentially non-functional, forcing users to browse hierarchically
- Users are completing intended tasks only 40% of the time
- Six-month post-launch target: 75% task completion rate

### Recommendations / Next Steps

1. **Immediate Actions:**
   - Conduct user testing with current site to baseline task completion metrics
   - Audit current content and create information architecture
   - Select modern CMS platform (WordPress, Webflow, or custom)

2. **Design Phase:**
   - Mobile-first design approach given traffic patterns
   - Simplify navigation to reduce clicks to key content
   - Implement robust search with filtering and autocomplete

3. **Technical Priorities:**
   - Performance optimization (target <2s load times)
   - Responsive design across all devices
   - Improved search infrastructure

4. **Success Metrics to Track:**
   - Task completion rate (baseline 40%, target 75%)
   - Bounce rate on key pages (reduce from 75% to <40%)
   - Page load times (target <2 seconds)
   - Mobile vs. desktop conversion parity

### Areas for Further Exploration

- Specific content strategy for improved product documentation
- Integration requirements with existing business systems
- Accessibility compliance requirements (WCAG 2.1 AA)
- Multilingual/localization needs for international users
```

## Conclusion

The Twenty Questions skill provides a powerful framework for systematic information gathering through structured, adaptive interviewing. By maintaining a progressively-updated artifact and dynamically generating context-aware questions, you can extract comprehensive knowledge on any topic while creating a valuable permanent record of the conversation.

Remember: The goal is not just to ask 20 questions, but to conduct a thoughtful exploration that builds understanding question by question, captured in a coherent and useful document.