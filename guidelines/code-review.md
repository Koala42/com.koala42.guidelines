# Code Review Guidelines

This document defines the processes for pull requests and code review. The goal is to improve code quality and collaboration speed.

## 1. Pull Request Requirements

### 1.1 PR Content

Every PR must include:

#### Required

- ✅ **Summary** – what changed and why
- ✅ **Functionality description** – what the feature/fix does
- ✅ **Testing instructions** – how to verify the changes work
- ✅ **Jira task reference** – link to the task/ticket

#### Optional (Recommended for Frontend)

- 📸 **Screenshots** – visual changes
- 🎥 **Video demo** – behavior demonstration (Loom, etc.)
- 🎨 **Figma link** – design reference
- 📝 **Expected UI behavior** – interaction details

### 1.2 PR Size

**Prefer smaller PRs:**

- ✅ Ideal: ~500 lines of changes or less
- ✅ Limited number of files
- ✅ Focused on a single concern

**Guidelines:**

- Break large changes into multiple PRs
- Initial PRs when bootstrapping a project can be larger

### 1.3 Response Time Expectations

⏱️ **Reviewers:**

- Should respond within **24 hours** (business days)
- Prioritize blocking PRs

⏱️ **Authors:**

- Should address feedback without unnecessary delays
- Respond to all comments promptly

💡 **Best Practice:** Handle code reviews at the start/end of day to avoid blocking others.

### 1.4 Reviewer Rights

Reviewers have the right to:

- ❌ **Request changes** – send PR back for rework
- ❌ **Reject PR** – if it doesn't meet quality standards or task requirements
- ✅ **Approve with conditions** – pre-approve with minor changes

## 2. PR Lifecycle

### Step-by-Step Process

#### 1. Self-Review

- Author reviews their own changes before opening PR
- Check for obvious issues, typos, debugging code
- It is possible to create draft before submitting PR
  
  - skips CI pipelines
  - used to review your changes
  
  ```
  🚧 Draft 🚧 xxx
  🚧 WIP 🚧 xxx
  ```


#### 2. AI Review (Upcoming)

- If automated AI code review is configured
- Author addresses AI-detected issues before human review

#### 3. Open PR

- Fill out PR description completely
- Assign reviewers

#### 4. Review

- Reviewer examines code and adds comments
- Status may be set to `changes required`
- Use constructive, specific feedback

#### 5. Address Feedback

- Author makes necessary changes
- Responds to all comments (see section 3)
- Pushes new commits

#### 6. Re-Review

- Author requests re-review after addressing feedback
- Reviewer checks if concerns were resolved

#### 7. Approval

**Process repeats [steps 4-6] until:**

✅ **Option A: Full Approval**

- Reviewer marks PR as `Approved`
- Ready to merge

✅ **Option B: Pre-Approve**

- Reviewer approves with minor conditions
- Author can merge after addressing listed items
- No additional review needed

#### 8. Merge

- Ensure CI pipeline is green ✅
- All comments resolved
- Squash or merge according to project convention

## 3. Handling Review Comments

### Response Requirements

Every comment must receive a response:

- 💬 **Detailed reply** – for questions or discussions
- ✅ **Acknowledgment** – simple confirmation ("Done", "Fixed", 👍)
- 🤔 **Clarification request** – if feedback is unclear

### Resolution Process

- All comments must be **resolved before merge**
- **Reviewer** marks comments as resolved (not author)
- Author should not resolve comments themselves unless explicitly agreed or PR is Pre-Approved

### Best Practices

- Be respectful and constructive
- Explain _why_ for significant feedback
- Suggest solutions, not just problems
- Ask questions to understand intent

## 4. Review Depth by Change Type

### 4.1 Core Features / Critical Changes

**Deep Review Required:**

- 🖥️ Run the project locally
- 🧪 Test functionality in runtime
- 🔍 Verify edge cases and error handling
- 📊 Check performance implications
- 🔒 Review security considerations

**When to use:**

- New core features
- Authentication/authorization changes
- Database migrations
- API contract changes
- Security-sensitive code

### 4.2 Minor Changes / Tight Budget

**Code Review Sufficient:**

- 👀 Thorough code examination
- 📝 Check tests coverage
- 💭 Verify logic correctness
- 🎯 Local testing optional

**When to use:**

- Small changes / fixes
- UI tweaks
- Documentation updates
- Minor refactoring
- Configuration changes

## 5. Summary of Key Principles

- ✅ **Consistency > personal preference**
- ✅ **Smaller PRs are better than large ones**
- ✅ **Every PR must be:**
  - Understandable
  - Testable
  - Traceable to requirements
- ✅ **Review is a shared responsibility, not a formality**
- ✅ **Reviewers have the right to reject or request rework**
- ✅ **Respond to all comments before merge**
- ✅ **Green CI pipeline is mandatory**

