# API Security Risk Analysis Report

## Project Overview
This project is a comprehensive API security risk assessment conducted as part of a cybersecurity training task. The assessment identifies and documents security vulnerabilities in a public API, following industry best practices and OWASP API Security Top 10 guidelines.

## Target API
- **Name:** JSONPlaceholder
- **URL:** https://jsonplaceholder.typicode.com
- **Type:** Fake REST API for testing
- **Documentation:** https://jsonplaceholder.typicode.com

## Tools Used
| Tool | Purpose |
|------|---------|
| Postman | API testing, request inspection, response analysis |
| Browser DevTools | Header inspection, network analysis |
| Google Docs | Report documentation |

## Scope & Methodology
### Assessment Type
Read-only security analysis - no exploitation attempts

### Testing Performed
- ✅ Authentication assessment
- ✅ Authorization testing (IDOR)
- ✅ Data exposure analysis
- ✅ Rate limiting validation
- ✅ Input validation testing

### OWASP Categories Covered
- API1:2023 - Broken Object Level Authorization
- API4:2023 - Unrestricted Resource Consumption
- API8:2023 - Security Misconfiguration
- API9:2023 - Improper Inventory Management

## Key Findings Summary

| Risk | Severity | Status |
|------|----------|--------|
| Missing Authentication | High | ✅ Confirmed |
| Authorization Bypass (IDOR) | High | ✅ Confirmed |
| Missing Rate Limiting | High | ✅ Confirmed |
| Excessive Data Exposure | Medium-High | ✅ Confirmed |
| Weak Input Validation | Medium | ✅ Confirmed |

## Report Contents
- [Full Security Analysis Report](API-Security-Risk-Analysis-Report.pdf)
- [Screenshots](Evidence/) - Evidence of all tests performed

## Testing Evidence
All tests were conducted ethically within the scope of public/demo APIs:

1. **No Authentication** - Headers inspected, no auth tokens present
2. **IDOR Vulnerability** - Accessed user 3 and user 7 without authorization
3. **Missing Rate Limiting** - 10+ rapid requests all returned 200 OK
4. **Excessive Data Exposure** - API returns GPS coordinates and full PII
5. **Input Validation** - Invalid data accepted (201 Created)

## Remediation Recommendations

### Priority 1 (Immediate)
- Implement authentication for all endpoints
- Add authorization checks for resource access
- Deploy rate limiting

### Priority 2 (Short-term)
- Reduce exposed data fields
- Add input validation

### Priority 3 (Long-term)
- Move to UUIDs for resource IDs
- Consider API gateway for unified security

## Ethical Compliance
This assessment was conducted with:
- ✅ Read-only operations only
- ✅ Public/demo API usage only
- ✅ No exploitation or bypass attempts
- ✅ No DoS or flooding tests


## Date
April 1, 2026
