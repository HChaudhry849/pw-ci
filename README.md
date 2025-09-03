# CI & Test Monitoring with Playwright and Datadog

This project demonstrates the integration of Playwright end-to-end tests within a Continuous Integration (CI) pipeline, utilizing Datadog's CI Visibility for comprehensive test monitoring and visualization.

---

## 🧪 Playwright Test Integration

Playwright is employed to execute browser automation tests, ensuring the reliability and performance of web applications.

### Installation

Install Playwright and its dependencies:

```bash
npm ci
npx playwright install --with-deps
```



Configure the number of workers to 1 for sequential test execution in CI environments:

```typescript
import { defineConfig } from '@playwright/test';

export default defineConfig({
  workers: process.env.CI ? 1 : undefined,
});
```



---

## 📊 Datadog CI Visibility Integration

Datadog's CI Visibility provides insights into test execution, failures, and trends over time.

### Setup

Install the Datadog CI CLI tool:

```bash
npm install -D @datadog/datadog-ci
```



Upload test results to Datadog:

```bash
npx playwright test --reporter=junit
npx datadog-ci tests upload test-results/*.xml
```



Ensure your Datadog API key is set as an environment variable:

```bash
export DATADOG_API_KEY=your_api_key
```



---

## 📈 Monitoring and Dashboards

Access the **CI Visibility → Tests** section in Datadog to view metrics such as test pass/fail rates, durations, and flaky tests.

Create custom dashboards to visualize test performance over time, aiding in the identification of trends and potential issues.

---

## 📄 License

This project is licensed under the MIT License.

---

Feel free to customize this README further to suit your project's specific requirements and configurations.
