Cloud Security – EBS Snapshot Audit (AWS)

Security-focused audit script for Amazon EC2 EBS snapshots, designed to support cloud hygiene, least privilege, and governance controls.

Why this exists

EBS snapshots are frequently overlooked assets in AWS environments.
Unmanaged snapshots can lead to:

data exposure

compliance violations

unnecessary cost

orphaned backups with unclear ownership

This project demonstrates how simple automation can support cloud security posture management.

Threat model (simplified)

Assets

EBS snapshots

EC2 volumes

Account metadata

Threats

Orphaned snapshots with sensitive data

Excessive IAM permissions

Lack of visibility and ownership

Controls

Read-only audit via AWS CLI

Minimal IAM policy

Deterministic output for logging

Security & Governance considerations

Principle of Least Privilege (IAM)

No write operations

No resource modification

Safe for regulated environments (audit-only)

Mapped controls:

CIS AWS Foundations

ISO 27001 – Asset Management

Backup & Retention hygiene

Required IAM permissions (minimum)
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeSnapshots",
        "ec2:DescribeVolumes"
      ],
      "Resource": "*"
    }
  ]
}

Use cases

Cloud security reviews

Incident response triage

Compliance audits

Cost and hygiene analysis

Disclaimer

This project is intended for educational and audit purposes only.
No resources are modified.

Author

Cloud Security Architect
Focused on governance, Zero Trust, and cloud risk management.
