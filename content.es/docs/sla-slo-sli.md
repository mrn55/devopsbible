---
title: "SLAs, SLOs, and SLIs"
date: 2024-10-02T11:37:59-07:00
type: "docs"
---

# Understanding SLAs, SLOs, and SLIs

## SLAs, SLOs, and SLIs Definitions and Relationships

In the context of service management and DevOps, **SLAs**, **SLOs**, and **SLIs** are essential components for managing service quality, ensuring reliability, and setting expectations between service providers and customers.

### 1. **Service Level Agreement (SLA)**

- **Definition**: A **Service Level Agreement (SLA)** is a formal contract between a service provider and its customers, specifying the level of service expected. It usually includes metrics such as uptime, response times, support availability, and penalties for non-compliance.
- **Purpose**: The SLA is a business-level agreement that defines the consequences if the service provider fails to meet the agreed-upon performance targets. It is legally binding and used to set clear expectations.
- **Example**: "The service will be available 99.9% of the time in a calendar month. Failure to meet this level of availability will result in a 10% reduction in the monthly fee."

### 2. **Service Level Objective (SLO)**

- **Definition**: A **Service Level Objective (SLO)** is a specific, measurable target within the SLA that a service provider aims to achieve. It’s a goal for the system’s reliability or performance and is usually defined in terms of availability, latency, or throughput.
- **Purpose**: SLOs set the internal targets that guide day-to-day operations to meet or exceed the SLA. It’s a less formal, internal standard, but critical for ensuring that teams are working towards specific performance benchmarks.
- **Example**: "The service will be available 99.95% of the time in a calendar month."

### 3. **Service Level Indicator (SLI)**

- **Definition**: A **Service Level Indicator (SLI)** is the actual measured performance metric that indicates the current level of service. SLIs are the data points used to evaluate whether the system meets the SLOs.
- **Purpose**: SLIs are the concrete metrics (like uptime percentage, response time) used to measure service performance. These are collected through monitoring tools and serve as the raw data for calculating whether SLOs are being met.
- **Example**: "In the past 30 days, the service has been available for 99.92% of the time."

---

## The Relationship Between SLAs, SLOs, and SLIs

- **SLIs (metrics)** feed into **SLOs (goals)**, and these SLOs support the fulfillment of **SLAs (contractual obligations)**.
- If SLIs show performance dropping below the SLO, corrective actions are taken before the SLA is violated.
- SLAs are external agreements, while SLOs are internal goals that ensure teams work toward meeting or exceeding SLA requirements. SLIs are the measurements used to track and monitor both SLO and SLA compliance.

Here’s how they relate:

- **SLA**: "What do we promise our customers?"
- **SLO**: "What goals should we meet internally to avoid breaching the SLA?"
- **SLI**: "How are we doing right now, and how can we measure it?"

---

## How to Use SLAs, SLOs, and SLIs to Manage Quality

1. **Define SLIs (Key Metrics to Measure Service Quality)**:
   - Identify the critical metrics that represent the health and performance of your system or service. Examples include:
     - **Uptime**: Percentage of time a service is operational (e.g., 99.95% uptime).
     - **Latency**: Time taken to respond to requests (e.g., 95% of requests respond within 100ms).
     - **Error Rate**: Percentage of failed requests (e.g., error rate <0.01%).
2. **Set SLOs (Internal Performance Targets)**:
   - Based on your SLIs, set realistic and achievable targets that reflect the desired quality level. These should align with customer expectations but be slightly more ambitious than your SLA to allow for buffer room.
   - For example:
     - If your SLA promises 99.9% uptime, your internal SLO could aim for 99.95%, ensuring you’re always within a safe margin.
3. **Monitor SLIs Continuously**:
   - Use monitoring tools like **Prometheus**, **Datadog**, **New Relic**, or **Grafana** to track SLIs in real time.
   - Set up alerts that trigger when an SLI starts approaching the thresholds defined by your SLOs. This proactive monitoring helps you take action before customers experience issues.
4. **Leverage Error Budgets**:
   - An **error budget** is the allowable margin for failure within the SLO. For example, if your SLO is 99.95% availability, the error budget is the 0.05% downtime allowance.
   - Error budgets guide decision-making on whether to focus on feature development (if you’re within the budget) or prioritize reliability improvements (if the budget is exceeded).
   - Example: "We have 4 hours of acceptable downtime per quarter based on our SLO. If this is exceeded, we pause new feature rollouts and focus on fixing reliability issues."
5. **Align SLOs with Business Objectives**:
   - Make sure your SLOs directly impact the business outcomes. If customers care about fast response times, latency should be a primary SLI. If uptime is critical, focus on availability.
   - Regularly revisit and adjust SLOs to reflect changes in customer expectations, technology, and business strategy.
6. **Use SLOs to Drive Operational Improvements**:
   - Analyze patterns in SLI data to spot trends or frequent issues. If your error budget is consistently exceeded, investigate root causes (e.g., bugs, infrastructure weaknesses).
   - Use the data from SLIs to improve infrastructure, code quality, and system reliability.
7. **Communicate Clearly**:
   - Ensure that SLAs are clearly communicated to customers and SLOs are well understood by internal teams.
   - Regularly report on SLA compliance to stakeholders and customers, demonstrating transparency and trustworthiness.

---

## Examples of SLA, SLO, and SLI in Practice

Let’s take a web service hosted in the cloud as an example:

- **SLA**: "The service will be available 99.9% of the time each month."
  - This means you promise customers that the service can be down for a maximum of about **43 minutes** per month (0.1%).
- **SLO**: "We aim for 99.95% availability."
  - Internally, you want to ensure that downtime doesn’t exceed **22 minutes** per month to create a buffer, giving you time to resolve incidents before violating the SLA.
- **SLI**: "Our monitoring system shows that availability over the last month was 99.93%."
  - The SLI indicates that your service was down for **30 minutes**, exceeding your SLO but still within the SLA. This means the team should investigate and improve reliability to avoid future SLA breaches.

---

## Benefits of Using SLAs, SLOs, and SLIs to Manage Quality

1. **Enhanced Reliability**:
   - With clear goals and real-time performance monitoring, you can ensure that your service is consistently reliable, improving customer satisfaction.
2. **Proactive Issue Detection**:
   - By monitoring SLIs, you can catch potential issues before they impact customers and breach SLAs, allowing for faster incident resolution.
3. **Data-Driven Decisions**:
   - SLOs and SLIs provide data that helps prioritize work. When error budgets are exceeded, teams focus on improving system stability instead of rolling out new features.
4. **Clear Accountability**:
   - SLAs set clear expectations for customers, while SLOs provide internal benchmarks that keep teams accountable to high-quality standards.
5. **Improved Customer Trust**:
   - By demonstrating commitment to service quality through transparent SLAs and consistent SLO compliance, companies can build and maintain customer trust.

---

## Conclusion

SLAs, SLOs, and SLIs work together to help organizations maintain a balance between reliability, performance, and innovation. By measuring key indicators (SLIs), setting internal performance goals (SLOs), and meeting contractual obligations (SLAs), teams can ensure high service quality, build trust with customers, and make informed decisions about resource allocation and product development.
