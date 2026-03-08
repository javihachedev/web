+++
categories = ['portfolio']
date = '2026-03-08T20:00:00+02:00'
draft = false
title = '👨‍💻 Mission Planning as a Service (2021 - now)'
+++

In this project I worked as **Technical Leader** in the migration of a complex satellite mission planning client application into a **modern web-based platform**. The original system — built as a desktop application for installation on client terminals — was widely used to plan and coordinate satellite ground segment operations. Developed over many years and proven across numerous space missions, it embodied significant mission planning logic and capabilities but was constrained by its architecture and deployment model, requiring specific installation configurations and limiting accessibility and scalability.

My responsibility was to **drive the technical strategy and execution of migrating this application toward a service-oriented web platform**. This involved decomposing a monolithic software into modular **modular, loosely coupled services** that could be consumed through APIs and operated within standard web browsers on any operating system. I led the design of a scalable backend service layer that exposed a robust REST API decoupling the core planning logic from the user interface. These APIs became the backbone of the new web platform, enabling integration with external tools and future extensions.

A key aspect of the modernization was the **containerization of the whole platform using Docker**, enabling consistent environments across development, testing, and production phases. By defining containerized services and standardized runtime configurations, we significantly improved deployment reproducibility, environment isolation, and operational flexibility. This Docker-based approach laid the foundation for cloud-native deployments and simplified system installation, upgrades, and scaling across different infrastructures.

Another central part of the migration was the development of a **new, intuitive web-based front-end**. Instead of maintaining a legacy client tied to specific hardware, we built a responsive, standards-based UI. This migration dramatically reduced client-side complexity and hardware dependency, greatly increasing accessibility and lowering operational barriers for new users.

From a leadership perspective, my role encompassed not only the technical design and architectural decisions but also **team coordination, cross-disciplinary collaboration, and stakeholder communication**. I organized and facilitated technical workshops, ensured alignment between backend and frontend development teams, and maintained clear technical roadmaps. This leadership ensured the technical evolution did not compromise the rich functionality and reliability the legacy system was known for, while positioning the product for future adoption as a cloud-native mission planning service.

Throughout the project, **quality, scalability, and maintainability** were our main priorities. The architectural transformation — supported by API-driven design and containerized deployment — established the foundation for delivering mission planning capabilities as a hosted service. This effort not only modernized the platform but also expanded its potential market reach, improved automation, and enabled easier integration into broader space operations ecosystems — representing a significant step toward true mission planning as a service.
