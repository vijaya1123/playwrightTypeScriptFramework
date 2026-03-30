Playwright TypeScript Automation Framework
A comprehensive automation testing framework built with Playwright and TypeScript, following industry best practices and design patterns.

Features
🎭 Playwright Integration: Latest Playwright test runner with TypeScript support
📄 Page Object Model: Organized and maintainable page classes
🔧 Base Page Class: Reusable common functionality
🧪 Test Fixtures: Dependency injection for page objects
📊 Logging System: Comprehensive logging with different levels
🗃️ Test Data Management: Centralized test data configuration
🌍 Multi-Environment Support: Easy environment switching
🌐 Cross-Browser Testing: Chrome, Firefox, Safari, and mobile browsers
📈 Rich Reporting: HTML, JSON, and JUnit reports
📸 Screenshots & Videos: Automatic capture on test failures
🔄 CI/CD Ready: Configured for continuous integration
Project Structure
playwright-typescript/
Prerequisites
Node.js (version 16 or higher)
PowerShell execution policy set to RemoteSigned (Windows)
Setup Instructions
1. Fix PowerShell Execution Policy (Windows Only)
If you encounter the npm script execution error, run this command in PowerShell as Administrator:

Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
2. Install Dependencies
npm install
3. Install Playwright Browsers
npm run install:browsers
Running Tests
Basic Test Execution
# Run all tests in headless mode
npm test

# Run tests with browser UI visible
npm run test:headed

# Run tests in debug mode
npm run test:debug

# Run tests with Playwright UI mode
npm run test:ui
View Test Reports
# Open HTML report
npm run report
Framework Components
Base Page Class
The BasePage class provides common functionality:

Element waiting and interaction methods
Screenshot capture
Navigation utilities
Error handling
Page Object Model
Example page class structure:

export class LoginPage  {
  private readonly usernameInput: Locator;
  private readonly passwordInput: Locator;
  
  constructor(page: Page) {
    super(page);
    this.usernameInput = page.locator('#username');
    this.passwordInput = page.locator('#password');
  }
  
  async login(username: string, password: string): Promise<void> {
    await this.fill(this.usernameInput, username);
    await this.fill(this.passwordInput, password);
  }
}

Environment Configuration
Multi-environment support with different configurations:

const config = Environment.getConfig();
// Returns different configs for dev/staging/production
Configuration
Playwright Configuration
The playwright.config.ts file includes:

Cross-browser testing setup
Test execution settings
Reporter configurations
Screenshot and video settings
TypeScript Configuration
The tsconfig.json includes:

Path mapping for clean imports
Strict type checking
ES2020 target with DOM support
Best Practices Implemented
Page Object Model: Separates page logic from test logic
DRY Principle: Reusable base classes and utilities
Type Safety: Full TypeScript support with strict typing
Logging: Comprehensive logging for debugging
Test Organization: Logical test grouping and fixtures
Environment Management: Easy environment switching
Error Handling: Robust error handling and reporting
Extending the Framework
Adding New Pages
Create a new page class extending BasePage
Define locators and methods
Add to test fixtures if needed
Adding New Tests
Create spec files in the tests/ directory
Import required fixtures and utilities
Follow the existing test patterns
Custom Utilities
Add new utilities in the src/utils/ directory following the established patterns.

Troubleshooting
Common Issues
PowerShell Script Execution: Ensure execution policy is set correctly
Browser Installation: Run npm run install:browsers if browsers are missing
TypeScript Errors: Check tsconfig.json configuration
Test Failures: Check logs and screenshots in test results
To run all Test:

npm run test:all
Contributing
Follow the established code structure
Add appropriate logging
Include tests for new functionality
Update documentation as needed
License
MIT License - See LICENSE file for details Advanced Automation framework for Playwright and Typescript
