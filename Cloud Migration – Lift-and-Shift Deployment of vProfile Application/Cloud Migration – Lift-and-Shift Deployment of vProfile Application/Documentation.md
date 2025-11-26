# Cloud Migration Documentation – vProfile Application

## 1. Introduction
This documentation explains the complete process of migrating the **vProfile monolithic application** to AWS using a **Lift-and-Shift strategy**.
The project focuses on operational execution rather than application development or CI/CD automation.

---

## 2. Migration Strategy
### Lift-and-Shift (Rehost)
- Application code remains unchanged
- Infrastructure is migrated to AWS
- Fast migration with minimal risk
- Commonly used for legacy workloads

---

## 3. Architecture Design
The application is deployed using a standard production-like architecture:

- Public subnets for Load Balancer
- Private subnets for application EC2 instances and database
- Load Balancer routes traffic to backend EC2 instances
- RDS provides a managed and reliable database layer

---

## 4. Infrastructure Components

### 4.1 EC2 Instances
- Host application services
- Deployed inside private subnets
- Secured via Security Groups
- Accessed through Load Balancer only

### 4.2 Load Balancer
- Distributes incoming traffic
- Improves availability
- Performs health checks

### 4.3 RDS
- Managed database service
- Provides data persistence
- Configured for application compatibility

### 4.4 Networking
- VPC with public and private subnets
- Route tables configured for controlled access
- NAT / Internet Gateway used appropriately

---

## 5. Security Configuration
- Security Groups restrict inbound and outbound traffic
- Only required ports are opened
- IAM roles used for secure permissions management
- No hardcoded credentials

---

## 6. Deployment Steps Summary
1. Create VPC and subnets
2. Configure route tables and gateways
3. Launch RDS instance
4. Launch EC2 application instances
5. Configure Load Balancer
6. Validate connectivity between services
7. Verify application functionality

---

## 7. Validation and Testing
- Application accessibility verified via Load Balancer DNS
- EC2 health checks validated
- Database connectivity confirmed
- Logs reviewed for errors

---

## 8. Operational Considerations
- Scalability via Load Balancer
- High availability through multiple instances
- Security through network isolation
- Monitoring readiness (CloudWatch-ready)

---

## 9. Project Scope
 Included:
- Cloud migration execution
- Infrastructure configuration
- Operational validation

 Not Included:
- CI/CD pipelines
- Infrastructure as Code
- Containerization or Kubernetes
- Microservices refactoring

---

## 10. Conclusion
This project demonstrates hands-on experience in **Cloud Operations and Cloud Migration**, focusing on real-world operational tasks such as infrastructure setup, security configuration, and workload migration.

It reflects responsibilities commonly expected from **CloudOps Engineers in production environments**.
