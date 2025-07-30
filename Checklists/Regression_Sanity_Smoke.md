# 🔄 Regression, Sanity & Smoke Checklist

This checklist helps structure rapid, targeted testing sessions after builds, deployments, or major code changes. It supports three levels of lightweight validation: smoke tests (basic system health), sanity checks (critical functionality), and regression sweeps (recent fixes and their impact). Useful for Web and Mobile QA pipelines.

## 🔥 Smoke Testing (High-level Stability)

- [ ] Application launches without crashes  
- [ ] Login/logout flows operate successfully  
- [ ] Key screens or pages are accessible  
- [ ] Basic navigation and routing works  
- [ ] Primary actions (e.g. search, submit) function as expected  
- [ ] UI components render without glitches or major layout issues  
- [ ] No blocking errors or missing assets upon load

## 🧠 Sanity Testing (Critical Functionality)

- [ ] New features show expected behavior in happy paths  
- [ ] Previous blockers or crashes no longer reproduce  
- [ ] Core user flows (e.g. sign-up, checkout) are fully usable  
- [ ] Form submissions and field validations work properly  
- [ ] Role-based access behaves correctly across environments  
- [ ] Major platform differences (Web vs Mobile) are verified  
- [ ] Build environment is configured and deploys without warnings

## 🧪 Regression Testing (Fix Verification)

- [ ] Previously reported bugs are confirmed resolved  
- [ ] Fixes do not break unrelated functionality  
- [ ] Linked components or modules behave consistently  
- [ ] API updates reflect correctly in UI (if applicable)  
- [ ] UI styling remains intact after version bump  
- [ ] Compatibility is preserved across browsers/devices  
- [ ] Edge cases related to recent fixes are retested

## ⏱ Execution & Reporting Tips

- [ ] Use checklist selectively based on deployment size  
- [ ] Document which sections were skipped and why  
- [ ] Log observations alongside corresponding items  
- [ ] Track regressions across releases to spot patterns  
- [ ] Share feedback with dev team early in the cycle  
- [ ] Include screenshots if visual regression is found

---

> 🧠 Tip: Automate parts of this checklist when possible, but always perform a manual pass for context-driven insights. These checks are essential to ship faster without compromising stability.