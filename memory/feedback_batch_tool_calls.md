---
name: batch_tool_calls
description: User prefers multiple independent tool calls batched together in one message rather than sequential permission requests
type: feedback
---

독립적인 tool call은 한 메시지에 묶어서 병렬로 실행할 것. line-by-line으로 권한 요청하지 말 것.

**Why:** 권한 요청이 너무 많으면 사용자 경험이 불편함.

**How to apply:** 독립적인 Read, Bash, Grep, Glob 등의 호출은 항상 하나의 응답 안에 묶어서 동시에 보낼 것. 결과가 서로 의존적일 때만 순차 실행.
