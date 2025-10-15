# 🛠️ Cloud Troubleshooting Scenarios

This file documents common cloud and Linux issues with step-by-step resolutions. It demonstrates practical problem-solving skills for entry-level IT and cloud support roles.

---

## 🔧 Scenario 1: EC2 Instance Won’t Start

- **Symptoms**: Instance stuck in “stopping” or “pending”
- **Root Cause**: Misconfigured shutdown behavior or attached volume issue
- **Resolution**:
  1. Check instance state in EC2 dashboard
  2. Review CloudWatch logs and system status checks
  3. Detach and reattach volume if needed
  4. Force stop via CLI: `aws ec2 stop-instances --instance-ids i-xxxx`

---

## 🌐 Scenario 2: S3 Bucket Access Denied

- **Symptoms**: “Access Denied” when trying to read/write
- **Root Cause**: IAM policy or bucket policy misconfiguration
- **Resolution**:
  1. Verify IAM role permissions (`s3:GetObject`, `s3:PutObject`)
  2. Check bucket policy for public access blocks
  3. Use AWS Policy Simulator to test access

---

## 🐧 Scenario 3: Linux Server Can’t Reach Internet

- **Symptoms**: `ping` fails, `apt update` times out
- **Root Cause**: Missing default gateway or DNS misconfiguration
- **Resolution**:
  1. Run `ip route` to check default route
  2. Add gateway: `sudo ip route add default via <gateway>`
  3. Check `/etc/resolv.conf` for valid DNS entries

---

## 🔐 Scenario 4: SSH Login Fails

- **Symptoms**: “Permission denied” or timeout
- **Root Cause**: Wrong key, user, or security group
- **Resolution**:
  1. Confirm correct `.pem` file and username (`ec2-user`, `ubuntu`, etc.)
  2. Check security group for port 22 access
  3. Use verbose mode: `ssh -v ec2-user@<ip> -i key.pem`

---

## 📌 Notes

- These scenarios reflect real-world issues encountered in cloud labs and entry-level support roles.
- Each includes root cause analysis and CLI-based resolution steps.
- Expand this file with new issues as you gain experience.
