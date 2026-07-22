# fintrust-secure-storage

Migrated a financial services firm's document storage to Azure with geo-redundant storage, least-privilege RBAC, and revocable time-boxed auditor access via stored access policies.

## The Problem
Picture a mid-sized financial services firm. KYC records, loan files, and quarterly audit reports - the most sensitive documents the business owns - living on employee laptops and shared USB drives.

The damage was predictable, and it happened:

1. A laptop failure destroyed the only copy of several loan files.
2. A junior staff member turned out to have access to high-net-worth client records completely unrelated to their role.
3. Every quarter, audit documents were emailed to external auditors as attachments - and copies still sit in those auditors' inboxes today, unrecoverable.

## Architecture diagram
![Architecture](architecture/FinTrust-Architecture.png)
