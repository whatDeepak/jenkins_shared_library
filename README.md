# Jenkins Shared Library

This repository provides a Jenkins Shared Library template that enables the reuse of code across multiple Jenkins Pipelines. With shared libraries, developers can encapsulate common logic into functions and classes, making it easier to maintain and apply across various Jenkins projects. This README outlines the steps required to set up, configure, and use a shared library within Jenkins.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Creating a Shared Library](#creating-a-shared-library)
3. [Using the Shared Library in Pipelines](#using-the-shared-library-in-pipelines)
4. [Important Notes](#important-notes)

---

## Introduction

Jenkins Shared Libraries are a powerful way to organize reusable pipeline code, which can be accessed by multiple pipelines and projects. By using shared libraries, you avoid duplicating logic across pipelines, making your Jenkins configuration more modular and maintainable. 

### Key Features:
- **Reusable Code**: Common logic can be centralized in a shared library, allowing it to be reused across multiple Jenkins jobs.
- **Groovy-based**: Shared libraries are written in Groovy, and each file within the library should have a `.groovy` extension.
- **Directory Structure**: The core of the shared library resides within the `vars` directory of your repository.

---

## Creating a Shared Library

To set up a shared library in Jenkins:

1. **Access Jenkins Dashboard**:
   - Log in to your Jenkins instance.

2. **Navigate to Global Library Configuration**:
   - From the main dashboard, go to **Manage Jenkins**.
   - Select **Configure System**.
   - Search for the section labeled **Global Pipeline Libraries**.

3. **Configure the Library**:
   - In the **Global Pipeline Libraries** section, click **Add** to define a new shared library.

   - **Name**: Set the library name (e.g., `Shared`).
   - **Default Version**: Specify the branch or version that Jenkins should use by default (e.g., `main`).
   - **Project Repository**: Provide the URL of the Git repository where the shared library code is stored (e.g., `https://github.com/yourusername/your-repository.git`).

4. **Save the Configuration**:
   - After filling in the required details, save the configuration. Jenkins is now ready to utilize the shared library in pipelines.

---

## Using the Shared Library in Pipelines

To utilize the shared library within a Jenkins pipeline:

1. **Declare the Shared Library in Your Pipeline Script**:
   - At the top of your Jenkins pipeline script, include the library using the `@Library` annotation.
   
     ```groovy
     @Library('Shared') _
     ```

   This line allows Jenkins to load the shared library with the specified name (`Shared`) into the pipeline, making its functions and classes available for use.

2. **Access Library Functions and Classes**:
   - You can now directly invoke functions and classes defined in the shared library in the pipeline.

---

## Important Notes

- **Directory Requirement**: Ensure that your library's code resides in the `vars` directory of the repository. This is where Jenkins expects to find the Groovy files for shared libraries.
- **File Extension**: All shared library files must use the `.groovy` file extension.
- **Library Naming Convention**: Use a unique and descriptive name for the library to avoid conflicts, especially if multiple shared libraries are in use.

---

By following these steps, you can create and use a Jenkins Shared Library, streamlining the pipeline code for enhanced reusability and maintainability.

---

I built this library with love for my fellow developers to simplify and share our Jenkins workflows. Feel free to fork it and make it yours! 🌻