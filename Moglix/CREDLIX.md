# Table of Contents

| S No. | Approach                                          |
| ----- | ------------------------------------------------- |
| 1     | [About Project](#About-Project)                   |
| 2     | [Project Configurations](#Project-Configurations) |
| 3     | [Contributers](#Contributers)                     |
| 4     | [Project Flow](#Project-Flow)                     |
| 5     | [My Contributions](#My-Contributions)             |

# About Project

**Introducing Credlix:** A revolutionary digital supply chain finance platform by Moglix that is transforming the way businesses access working capital. Designed to provide fast, collateral-free financing solutions, Credlix caters to enterprises, suppliers, and exporters across India and Southeast Asia.

With a proven track record of supporting over 700 enterprises and 16,000 SMEs exporting to 53 countries, Credlix harnesses Moglix's deep expertise in supply chain transformation. The platform offers a range of innovative services, including early payment, vendor finance, channel finance, invoice discounting, and purchase order finance, ensuring seamless movement in domestic supply chains and export financing.

Notably, Credlix features two key projects: **Nuphi** and **Exim**, which enhance its capabilities and broaden its service offerings, making it a one-stop solution for all your financing needs.

**[⬆ Back to Top](#table-of-contents)**

# Project Configurations

### Configurations of Nuphi - Before Angular Update

| Requirement | Version          |
| ----------- | ---------------- |
| Node.js     | 16.14.2 or later |
| Angular CLI | 9.1.7            |
| npm         | 8.5.0 or later   |
| TypeScript  | 3.8.3            |

### Configurations of Nuphi - After Angular Update

| Requirement | Version          |
| ----------- | ---------------- |
| Node.js     | 16.14.2 or later |
| Angular CLI | 12.2.13          |
| npm         | 8.5.0 or later   |
| TypeScript  | 4.3.5            |

### Configurations of Exim - Before Angular Update

| Requirement | Version          |
| ----------- | ---------------- |
| Node.js     | 16.14.2 or later |
| Angular CLI | 7.3.10           |
| npm         | 8.5.0 or later   |
| TypeScript  | 3.2.2            |

**[⬆ Back to Top](#table-of-contents)**

# Contributers
![Sudhanshu](https://github.com/user-attachments/assets/c82146cf-2c47-47e7-b4c3-3ed2e8dd8ccd)

<p align="center">
    <table>
        <tr>
            <td align="center">
                <a href="https://www.linkedin.com/in/sanjay9616/" target="_blank" title="Sanjay Kumar">
                    <img src="https://github.com/user-attachments/assets/959ee001-8a02-407e-af5d-3a61fae65679" alt="Sanjay Kumar" width="150" height="150" />
                    <br>
                    <b>Sanjay Kumar</b><br>
                    <div>Web Developer</div>
                </a>
            </td>
            <td align="center">
                <a href="https://www.linkedin.com/in/sudh-pathak/" target="_blank" title="Sudhanshu Kumar Pathak">
                    <img src="https://github.com/user-attachments/assets/0d70afb0-dffd-4e49-9b7b-e92752c3f08e" alt="Sudhanshu Kumar Pathak" width="150" height="150" />
                    <br>
                    <b>Sudhanshu Kumar Pathak</b><br>
                    <div>Software Engineer</div>
                </a>
            </td>
            <td align="center">
                <a href="https://www.linkedin.com/in/aditya-maurya-703876192/" target="_blank" title="Aditya Maurya">
                    <img src="https://github.com/user-attachments/assets/aa877e20-cf4e-4709-9159-4bfedd0b84b8" alt="Aditya Maurya" width="150" height="150" />
                    <br>
                    <b>Aditya Maurya</b><br>
                    <div>Software Development Engineer II</div>
                </a>
            </td>
        </tr>
    </table>
</p>

**[⬆ Back to Top](#table-of-contents)**

# Project Flow

**[⬆ Back to Top](#table-of-contents)**

# My Contributions

## Implementation of Login and Signup Flow for Domestic and Exporter

**Description:**

I developed the login and signup flow for both domestic users and exporters in the Credlix platform using Angular Material design. The implementation focused on a seamless user experience, ensuring that the UI was intuitive and responsive. This involved designing and integrating form components with validation, authentication services, and conditional routing based on user roles.

**Impact:**

- Improved User Experience: The use of Angular Material provided a modern and accessible UI, enhancing the overall look and feel of the platform.
- Streamlined Onboarding: A clear and efficient signup process reduced the time users spent registering, contributing to higher conversion rates for new users.
- Role-Based Functionality: The separation of flows for domestic and exporter users allowed for a more tailored experience, catering to the specific needs of each user type.

## Implementation of Proforma Invoice Calculation

**Description:**

I developed the proforma invoice calculation functionality, automating the generation of invoices based on user inputs, including product details, pricing, taxes, and discounts. This implementation ensures accuracy in invoice generation and reduces manual intervention, enabling a smoother process for users to preview and manage their proforma invoices.

**Impact:**

Increased Efficiency: Automated calculations minimized manual errors, speeding up the invoice generation process.
Improved Accuracy: The system ensured precise calculations, leading to better compliance and customer trust.
Enhanced User Satisfaction: Users experienced a more streamlined approach to creating and managing invoices, improving overall satisfaction with the platform.

## Angular Version 7 to 12 with Strict Mode Enabled

**Description:**

The upgrade from Angular 7 to Angular 12 involved a series of systematic steps to modernize the application and incorporate the latest Angular features and best practices. This process ensured that the application remained up-to-date, maintainable, and efficient. The decision to enable strict mode further reinforced type safety and code robustness, aligning with Angular's recommendations for optimal development practices.

**Key Steps Involved:**

- Version Migration:
    - Upgrade Angular CLI: Updated Angular CLI from version 7 to version 12 by using incremental updates (version-by-version) to avoid breaking changes. This ensured a smooth transition and compatibility across versions.
    - Refactor for Deprecated Features: Addressed deprecated APIs and features as per Angular's migration guidelines. This included updating libraries, RxJS imports, and HTTP client syntax changes, ensuring all modules were compliant with Angular 12 standards.
    - Third-Party Library Updates: Updated third-party dependencies and Angular Material to the latest versions to ensure compatibility with Angular 12.
- Enabled Strict Mode:
    - Enabling strict mode involved setting the strict flag to true in the tsconfig.json file. This introduced stricter type checks, including:
        - Strict Type Checking: More precise inference of types, helping to catch potential runtime errors at compile time.
        - Null Safety: Detection of null and undefined values at an early stage, preventing null reference errors in production.
        - No Implicit Any: Enforcing explicit typing for all variables and functions, ensuring the code is strongly typed.
        - Strict Template Checking: Strengthened template binding checks to align with the component’s types, ensuring that templates are correctly bound to component logic.
- Tree-Shakable Modules: Angular 12 improved tree-shaking capabilities, which meant unused code was automatically removed from the production build, reducing the bundle size.
- Optimized Build Process:
    - Faster Builds: Angular 12 introduced faster compilation with Ivy, which significantly improved development build times and reduced bundle sizes.
    - Improved Localization: The i18n (internationalization) capabilities were enhanced, making the app more adaptable to multiple languages, which was useful for scaling to international markets.
- TypeScript Upgrade: Upgraded the TypeScript version to 4.8.4, which unlocked new language features, better type inference, and faster builds.

**Impact:**

- Performance Boost: The Ivy engine in Angular 12 improved compilation times and memory consumption, making the app faster to develop, build, and run.
- Code Consistency and Safety: Strict mode introduced stronger type-checking throughout the application, which reduced bugs, increased maintainability, and made refactoring easier.
- Enhanced Developer Experience: By catching more errors during compile time and optimizing the build processes, the development cycle became smoother and more reliable.
- Smaller Bundle Size: Tree-shaking and optimizations in Angular 12 reduced the overall bundle size, enhancing the application's load times and improving the user experience.
- Scalability: The update future-proofed the codebase, making it easier to adopt future Angular updates and scale the application with new features and optimizations.

**[⬆ Back to Top](#table-of-contents)**
