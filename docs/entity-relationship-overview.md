# Entity Relationship Overview

This document describes a demonstration entity relationship model for environmental, utility, compliance, and infrastructure software systems.

The purpose is to show how environmental platforms can connect operational records, evidence, monitoring data, facilities, permits, incidents, and reporting workflows.

## Core Entities

```text
Facility
Permit
Monitoring Event
Inspection
Evidence Record
Incident
Corrective Action
Report Submission
User / Organization
Audit Event
```

## High-Level Relationship Pattern

```text
Organization
  -> Facility
      -> Permit
          -> Permit Condition
          -> Reporting Obligation
      -> Monitoring Event
          -> Evidence Record
      -> Inspection
          -> Finding
          -> Corrective Action
      -> Incident
          -> Response Action
          -> Public Notification
      -> Report Submission
          -> Evidence Record
          -> Approval Record
```

## Facility

A facility is the central operational location or regulated asset. It may represent a water treatment plant, wastewater treatment plant, industrial site, monitoring station, landfill, public infrastructure site, or other regulated location.

Facilities typically connect to:

- permits
- monitoring locations
- inspections
- incidents
- compliance reports
- evidence records
- GIS layers

## Permit

A permit defines authorization, obligations, limits, reporting duties, evidence expectations, and renewal context.

Permits typically connect to:

- facility
- permit conditions
- monitoring events
- reporting obligations
- evidence records
- report submissions

## Monitoring Event

A monitoring event represents a sample, sensor reading, field measurement, lab result, remote sensing observation, or inspection observation.

Monitoring events typically connect to:

- facility
- monitoring location
- parameters
- thresholds
- evidence records
- compliance reports

## Evidence Record

An evidence record is a structured reference to supporting material. It may represent a lab report, document, photo, map layer, exported sensor record, signed approval, inspection artifact, or correspondence.

Evidence records typically connect to:

- permit
- monitoring event
- inspection
- incident
- report submission
- corrective action

## Incident

An incident represents a reported issue, exceedance, spill, public complaint, equipment failure, service disruption, or emergency event.

Incidents typically connect to:

- facility
- response actions
- evidence records
- public notifications
- corrective actions
- audit trail events

## Audit Event

Audit events preserve system accountability. They document creation, updates, submissions, reviews, approvals, rejections, publication, archival, and access-sensitive actions.

Audit events should generally capture:

- actor
- action
- timestamp
- related entity
- previous value when appropriate
- new value when appropriate
- reason or notes
- source system

## Design Principle

Environmental platforms should not treat records as isolated tables. They should preserve operational context and decision history across the full lifecycle.

## Notice

This overview is a fictional, public demonstration pattern. It is not legal, regulatory, engineering, environmental, or cybersecurity advice.
