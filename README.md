# Formal zero public exposure CI/CD

This project is my best attempt at creating a CI/CD pipeline with zero public exposure, verified formally. The pipeline is written in Terraform and runs on AWS.

A system is publicly exposed if and only if the internet reaches some asset in the configuration the system admits.

[Principles](docs/principles.md) defines the words in that sentence.
