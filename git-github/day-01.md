# Git Day 01 - Version Control Fundamentals
## 1.What is Version Control?

Version Control is a system that tracks changes in files over time.

It allows you to:

Track who made changes

Restore previous versions

Maintain project history

Collaborate without overwriting others’ work

Without version control, projects become messy and unmanageable.

## 2.Why Version Control is Needed

In real projects:

Multiple developers work on the same code

Code changes daily

Bugs need rollback

Features evolve over time

Without version control:

Files get overwritten

No history tracking

No safe recovery

Version control provides safety and structure.

## 3.Types of Version Control Systems
### 3.1 Centralized Version Control (CVCS)

Characteristics:

Single central server

Developers connect to server

Internet required

Single point of failure

Examples:

Subversion

CVS

If the server fails, development stops.

### 3.2 Distributed Version Control (DVCS)

Characteristics:

Every developer has full repository copy

Work offline

No single point of failure

Faster performance

Example:

Git

This model is more reliable and scalable.

## 4.Why Git Was Created

Git was created in 2005 by:

Linus Torvalds

The Linux kernel project needed:

High speed

Data integrity

Strong branching support

Distributed workflow

Git was built to solve real engineering problems, not theoretical ones.

## 5.How Git Actually Works

Git does not store file differences in the traditional way.

Git stores snapshots of the project.

Each commit:

Captures the complete state of the project

Generates a unique SHA hash

Stores data inside the .git directory

Core areas in Git:

Working Directory

Staging Area

Local Repository

Understanding this architecture is critical.

## 6.Git File State Machine

Every file in Git moves through these states:

1.Untracked
2.Modified
3.Staged
4.Committed

Flow:

Untracked → git add → Staged
Modified → git add → Staged
Staged → git commit → Committed

After modifying again → file becomes Modified.

If you do not understand this cycle, you will misuse Git commands.

## 7.Git vs GitHub
Git

Local version control system

Works offline

Tracks file changes

Installed on machine

GitHub

GitHub

Cloud platform to host Git repositories

Enables collaboration

Supports Pull Requests and CI/CD

Git is the tool.
GitHub is the hosting platform.

## 8.DevOps Connection

Git is used in:

Infrastructure as Code

CI/CD pipelines

Docker projects

Kubernetes manifests

Automation scripts

Without Git, DevOps workflow is incomplete.

## 9.Reflection

Today I learned:

What version control means

Difference between centralized and distributed systems

Why Git was created

How Git stores snapshots

Git file lifecycle

Areas to revise:

Internal working of .git directory

Snapshot vs difference storage
