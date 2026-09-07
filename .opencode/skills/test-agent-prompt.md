---
name: test-agent-prompt
description: Test and validate AI agent prompts for accuracy and safety
trigger: "Test agent prompt"
---

# Test Agent Prompt

## Steps

1. **Define Test Cases**
   - Normal vulnerability: Expected output
   - Edge case: Unusual asset configuration
   - Malicious input: XSS/SQL injection attempt
   - Ambiguous input: Multiple interpretations

2. **Setup Testing Framework**
   ```bash
   npm install -D jest @testing-library/react
   ```

3. **Create Prompt Variations**
   - System prompt (base behavior)
   - Temperature settings (creativity vs consistency)
   - Token limits (output length)
   - Constraint injection (safety guardrails)

4. **Execute Test Cases**
   - Pass each test case to agent
   - Collect responses
   - Measure latency and token usage
   - Validate safety constraints

5. **Evaluate Output Quality**
   - Accuracy against known answers
   - Tone and professionalism
   - Relevance to security context
   - No hallucinations or false data

6. **Document Results**
   - Create test report with metrics
   - Flag unsafe outputs
   - Recommend prompt improvements
   - Version the approved prompt

## Success Criteria
- All normal cases pass
- Edge cases handled gracefully
- No safety constraint violations
- Average latency < 2 seconds
- Accuracy rate ≥ 95%
- All test cases documented
