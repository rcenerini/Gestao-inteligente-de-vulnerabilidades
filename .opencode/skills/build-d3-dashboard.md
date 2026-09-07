---
name: build-d3-dashboard
description: Create interactive D3.js vulnerability dashboard
trigger: "Build vulnerability dashboard"
---

# Build D3.js Vulnerability Dashboard

## Steps

1. **Setup React Component Structure**
   ```bash
   mkdir -p src/components/dashboard
   npm install d3 react-d3-library
   ```

2. **Create Dashboard Component**
   - Main dashboard wrapper component
   - Responsive grid layout (12 columns)
   - Dark mode support for security operations

3. **Build Chart Components**
   - Vulnerability severity trend (time-series)
   - Asset coverage heatmap
   - Remediation progress gauge
   - Top vulnerabilities bar chart
   - Compliance score radar chart

4. **Integrate Real-time Data**
   - WebSocket connection to API
   - Auto-refresh every 5 minutes
   - Cache local data for offline support

5. **Add Interactive Features**
   - Drill-down from summary to details
   - Filter by team, asset type, severity
   - Export as PDF/PNG
   - Custom date range selector

6. **Implement Accessibility**
   - WCAG 2.1 AA compliance
   - Keyboard navigation support
   - Screen reader friendly

## Success Criteria
- All 5 chart types rendered correctly
- Real-time data updates working
- Dashboard loads in < 3 seconds
- Mobile responsive
- Accessibility audit passes
