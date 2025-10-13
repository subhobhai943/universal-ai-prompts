# 🔒 Secure API Development Prompts

> **Security First**: These prompts generate production-ready, secure APIs following industry best practices and security standards.

## 📋 Description

Comprehensive prompts for developing secure REST and GraphQL APIs with built-in security controls, proper authentication, authorization, input validation, and compliance with security standards like OWASP API Security Top 10.

## 🎯 Purpose

- **Secure by Design**: Generate APIs with security built-in from the start
- **OWASP Compliance**: Follow OWASP API Security Top 10 guidelines
- **Authentication & Authorization**: Implement robust access controls
- **Input Validation**: Prevent injection attacks and malformed requests
- **Error Handling**: Secure error responses without information leakage
- **Rate Limiting**: Protect against abuse and DoS attacks
- **Audit Logging**: Comprehensive security event tracking

## 🤖 Compatible Models

- [x] **ChatGPT (GPT-4)** - Excellent for complex security implementations
- [x] **Claude 3.5 Sonnet** - Great for security analysis and best practices
- [x] **GitHub Copilot** - Real-time secure coding assistance
- [x] **Code Llama** - Good for language-specific implementations
- [x] **Gemini Pro** - Solid for documentation and examples

## 📋 Prerequisites

- Understanding of RESTful API principles
- Knowledge of chosen programming language/framework
- Basic security concepts (authentication, authorization, etc.)
- Development environment setup
- Database or data storage solution

---

## 💡 Core API Security Prompts

### 1. Complete Secure REST API (Python/Flask)

```
You are a senior security engineer creating a production-ready REST API. Generate a comprehensive secure API implementation using Python Flask with the following security requirements:

**SECURITY FRAMEWORK:**
- JWT-based authentication with refresh tokens
- Role-based access control (RBAC) with fine-grained permissions
- Input validation using marshmallow schemas
- SQL injection prevention with SQLAlchemy ORM
- XSS protection with output encoding
- CSRF protection for state-changing operations
- Rate limiting per endpoint and user
- Security headers (HSTS, CSP, X-Frame-Options, etc.)
- Request/response logging for security auditing
- API versioning with backward compatibility

**API ENDPOINTS TO IMPLEMENT:**
1. POST /auth/login - User authentication
2. POST /auth/refresh - Token refresh
3. GET /users - List users (admin only)
4. GET /users/{id} - Get user details (self or admin)
5. POST /users - Create user (admin only)
6. PUT /users/{id} - Update user (self or admin)
7. DELETE /users/{id} - Delete user (admin only)
8. GET /health - Health check endpoint

**SECURITY REQUIREMENTS:**
- Password hashing with bcrypt (minimum 12 rounds)
- Account lockout after 5 failed attempts
- Session timeout and automatic logout
- Input sanitization and validation
- Secure password requirements
- Multi-factor authentication support
- API key authentication for service-to-service
- Comprehensive error handling without information leakage
- Request size limits and timeout protection
- SQL query parameterization

**COMPLIANCE REQUIREMENTS:**
- OWASP API Security Top 10 compliance
- PCI DSS considerations for payment data
- GDPR compliance for EU users
- SOC 2 Type II audit trail requirements

**ADDITIONAL FEATURES:**
- Swagger/OpenAPI documentation with security schemas
- Health monitoring and metrics endpoints
- Database migration scripts
- Environment-based configuration
- Docker containerization with security hardening
- Unit and integration tests with security test cases

Include comprehensive inline documentation, security comments, and deployment guidelines. Generate production-ready code with proper error handling, logging, and monitoring.
```

### 2. Secure GraphQL API Implementation

```
Create a production-grade GraphQL API with comprehensive security controls. Implement the following security-first GraphQL server:

**GRAPHQL SECURITY FRAMEWORK:**
- Query complexity analysis and depth limiting
- Query whitelisting for production environments
- Field-level authorization with context-aware permissions
- Resource-based access control
- Query cost analysis and budgeting
- Introspection disabling in production
- Timeout protection for long-running queries
- Query deduplication and caching
- Schema validation and type safety
- Custom scalar validation for sensitive data types

**SCHEMA DESIGN:**
```graphql
type User {
  id: ID!
  username: String!
  email: String!
  roles: [Role!]!
  profile: UserProfile
  createdAt: DateTime!
  lastLogin: DateTime
}

type Role {
  id: ID!
  name: String!
  permissions: [Permission!]!
}

type Query {
  me: User
  users(first: Int, after: String, filter: UserFilter): UserConnection
  user(id: ID!): User
}

type Mutation {
  login(input: LoginInput!): AuthPayload!
  register(input: RegisterInput!): AuthPayload!
  updateProfile(input: UpdateProfileInput!): User!
  changePassword(input: ChangePasswordInput!): Boolean!
}
```

**SECURITY IMPLEMENTATION REQUIREMENTS:**
- JWT authentication with proper validation
- Context-based authorization middleware
- Input sanitization for all resolver arguments
- SQL injection prevention in database queries
- XSS protection in response data
- Rate limiting per query type and user
- Comprehensive audit logging
- Error masking to prevent information disclosure
- CORS configuration for web clients
- Schema-level security annotations

**RESOLVER SECURITY PATTERNS:**
- Dataloader pattern for N+1 query prevention
- Pagination limits and cursor validation
- Field-level caching with security context
- Async/await error handling
- Database connection pooling and timeout handling
- Memory usage monitoring and limits

**DEPLOYMENT SECURITY:**
- Environment variable management
- Docker security hardening
- Health check endpoints
- Metrics and monitoring integration
- Structured logging with correlation IDs
- Performance monitoring and alerting

Implement using [FRAMEWORK] (Node.js/Apollo, Python/Graphene, etc.) with comprehensive test coverage including security test cases.
```

### 3. Microservices API Gateway Security

```
Design and implement a secure API Gateway for microservices architecture with comprehensive security controls and service mesh integration:

**API GATEWAY SECURITY ARCHITECTURE:**
- Centralized authentication and token validation
- Service-to-service authentication with mTLS
- Dynamic route discovery and health checking
- Circuit breaker pattern for resilience
- Distributed tracing for security audit trails
- Centralized logging and monitoring
- API version management and backward compatibility
- Request/response transformation and validation
- Traffic shaping and throttling
- Geographic and IP-based access controls

**AUTHENTICATION & AUTHORIZATION:**
- Multiple authentication methods (JWT, OAuth2, API Keys)
- Integration with identity providers (Auth0, Okta, AWS Cognito)
- Role-based and attribute-based access control
- Dynamic policy enforcement
- Token introspection and validation
- Refresh token rotation and revocation
- Service account management
- Cross-origin resource sharing (CORS) handling

**SECURITY MIDDLEWARE STACK:**
1. Request ID generation and correlation
2. Rate limiting and DDoS protection
3. Input validation and sanitization
4. Authentication and token validation
5. Authorization policy enforcement
6. Request/response logging
7. Security header injection
8. Error handling and response filtering

**MICROSERVICES INTEGRATION:**
- Service discovery and registration
- Health check aggregation
- Load balancing with security considerations
- Timeout and retry policies
- Request routing based on security context
- Service-level metrics and monitoring
- Canary deployment support
- Blue-green deployment coordination

**CONFIGURATION MANAGEMENT:**
```yaml
gateway:
  security:
    authentication:
      jwt:
        secret: ${JWT_SECRET}
        expiration: 3600
        refresh_expiration: 86400
      oauth2:
        providers:
          - name: google
            client_id: ${GOOGLE_CLIENT_ID}
            client_secret: ${GOOGLE_CLIENT_SECRET}
    rate_limiting:
      default_rpm: 1000
      burst_capacity: 100
    cors:
      allowed_origins: ${ALLOWED_ORIGINS}
      allowed_methods: ["GET", "POST", "PUT", "DELETE"]
      allowed_headers: ["Authorization", "Content-Type"]
  routes:
    - path: /api/users/*
      service: user-service
      auth_required: true
      roles: ["user", "admin"]
      rate_limit: 500
```

**MONITORING & OBSERVABILITY:**
- Request/response metrics collection
- Security event alerting
- Performance monitoring and SLA tracking
- Error rate monitoring and alerting
- Distributed tracing integration
- Audit log aggregation and analysis
- Real-time dashboard for security metrics

Implement using [TECHNOLOGY] (Kong, Ambassador, Istio, etc.) with comprehensive documentation and operational runbooks.
```

### 4. OAuth 2.0 / OpenID Connect Implementation

```
Implement a complete OAuth 2.0 Authorization Server with OpenID Connect support following security best practices and RFC specifications:

**OAUTH 2.0 SECURITY IMPLEMENTATION:**
- Authorization Code flow with PKCE (RFC 7636)
- Client Credentials flow for service-to-service
- Resource Owner Password Credentials (with restrictions)
- Implicit flow deprecation and migration strategy
- Refresh token rotation and binding
- Scope-based access control
- Dynamic client registration (RFC 7591)
- Token introspection (RFC 7662)
- Token revocation (RFC 7009)
- Device Authorization Grant (RFC 8628)

**OPENID CONNECT FEATURES:**
- ID token generation and validation
- UserInfo endpoint with claims mapping
- Discovery endpoint (/.well-known/openid_configuration)
- JWT signing with key rotation
- Claims-based authorization
- Session management and logout
- Prompt handling (login, consent, select_account)
- Response types and modes support

**SECURITY CONTROLS:**
- Client authentication methods (client_secret_basic, client_secret_post, private_key_jwt)
- Redirect URI validation and strict matching
- State parameter enforcement for CSRF protection
- Nonce validation for replay attack prevention
- Authorization code time-based expiration
- Access token short lifespan with refresh capability
- Consent management and user control
- Brute force protection on token endpoints
- Rate limiting per client and endpoint
- Comprehensive audit logging

**CLIENT MANAGEMENT:**
```json
{
  "client_id": "web-app-123",
  "client_secret": "hashed_secret",
  "client_name": "Web Application",
  "redirect_uris": ["https://app.example.com/callback"],
  "allowed_scopes": ["openid", "profile", "email", "read:users"],
  "grant_types": ["authorization_code", "refresh_token"],
  "response_types": ["code"],
  "token_endpoint_auth_method": "client_secret_basic",
  "require_auth_time": true,
  "default_max_age": 86400,
  "trusted": false
}
```

**TOKEN MANAGEMENT:**
- JWT access tokens with standard claims
- Opaque refresh tokens with secure storage
- Token binding and proof-of-possession
- Token exchange (RFC 8693) for delegation scenarios
- Audience validation and restriction
- Issuer identification and validation
- Key rotation and cryptographic agility
- Token lifecycle management

**INTEGRATION ENDPOINTS:**
- GET /.well-known/openid_configuration
- POST /oauth/authorize
- POST /oauth/token
- POST /oauth/revoke
- POST /oauth/introspect
- GET /oauth/userinfo
- GET /oauth/jwks
- POST /oauth/logout

**DEPLOYMENT CONSIDERATIONS:**
- High availability and load balancing
- Database security and encryption
- TLS configuration and certificate management
- Environment-specific configuration
- Monitoring and alerting setup
- Backup and disaster recovery
- Performance optimization
- Security testing and validation

Include comprehensive test suite covering security scenarios, edge cases, and compliance requirements.
```

### 5. API Security Testing & Validation

```
Generate comprehensive security testing suite for API security validation including automated testing, security scanning, and compliance verification:

**SECURITY TEST FRAMEWORK:**
- Authentication and authorization testing
- Input validation and injection testing
- Rate limiting and DoS protection testing
- Session management security testing
- CORS and security header validation
- Error handling and information disclosure testing
- Business logic security testing
- API abuse and misuse testing

**AUTOMATED SECURITY TESTS:**
```python
import pytest
import requests
import jwt
from faker import Faker
import time

class TestAPISecuritySuite:
    
    def test_authentication_bypass_attempts(self):
        """Test various authentication bypass techniques"""
        bypass_attempts = [
            {},  # No auth header
            {"Authorization": ""},  # Empty auth
            {"Authorization": "Bearer "},  # Empty token
            {"Authorization": "Bearer invalid_token"},  # Invalid token
            {"Authorization": "Basic invalid"},  # Wrong auth type
        ]
        
        for headers in bypass_attempts:
            response = requests.get(f"{self.base_url}/api/users", headers=headers)
            assert response.status_code == 401
            assert "error" in response.json()
    
    def test_sql_injection_attempts(self):
        """Test SQL injection in various parameters"""
        injection_payloads = [
            "'; DROP TABLE users; --",
            "' OR '1'='1",
            "' UNION SELECT * FROM users --",
            "'; EXEC xp_cmdshell('dir'); --"
        ]
        
        for payload in injection_payloads:
            response = requests.get(f"{self.base_url}/api/users/{payload}")
            assert response.status_code in [400, 404]  # Should not return data
    
    def test_rate_limiting_enforcement(self):
        """Test rate limiting controls"""
        for i in range(150):  # Exceed rate limit
            response = requests.get(f"{self.base_url}/api/users")
            if response.status_code == 429:
                assert "rate limit" in response.json().get("error", "").lower()
                break
        else:
            pytest.fail("Rate limiting not enforced")
```

**OWASP API TOP 10 TESTING:**
1. API1:2023 - Broken Object Level Authorization
2. API2:2023 - Broken Authentication
3. API3:2023 - Broken Object Property Level Authorization
4. API4:2023 - Unrestricted Resource Consumption
5. API5:2023 - Broken Function Level Authorization
6. API6:2023 - Unrestricted Access to Sensitive Business Flows
7. API7:2023 - Server Side Request Forgery
8. API8:2023 - Security Misconfiguration
9. API9:2023 - Improper Inventory Management
10. API10:2023 - Unsafe Consumption of APIs

**PERFORMANCE & LOAD TESTING:**
- Baseline performance benchmarking
- Stress testing with security controls enabled
- Memory usage monitoring during attacks
- Database connection pool exhaustion testing
- Concurrent request handling validation
- Resource cleanup verification

**COMPLIANCE VALIDATION:**
- PCI DSS API security requirements
- GDPR data protection validation
- SOX compliance for financial APIs
- HIPAA compliance for healthcare APIs
- SOC 2 security control validation

Include automated security scanning integration with tools like OWASP ZAP, Burp Suite, and custom security validators.
```

---

## 🔧 Framework-Specific Examples

### Node.js/Express Security Middleware

```javascript
const express = require('express');
const helmet = require('helmet');
const rateLimit = require('express-rate-limit');
const jwt = require('jsonwebtoken');
const validator = require('validator');

const app = express();

// Security middleware stack
app.use(helmet({
  contentSecurityPolicy: {
    directives: {
      defaultSrc: ["'self'"],
      scriptSrc: ["'self'"],
      styleSrc: ["'self'", "'unsafe-inline'"],
      imgSrc: ["'self'", "data:", "https:"],
    },
  },
  hsts: {
    maxAge: 31536000,
    includeSubDomains: true,
    preload: true
  }
}));

// Rate limiting
const limiter = rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100, // limit each IP to 100 requests per windowMs
  message: 'Too many requests from this IP',
  standardHeaders: true,
  legacyHeaders: false,
});
app.use('/api/', limiter);

// Authentication middleware
const authenticateToken = (req, res, next) => {
  const authHeader = req.headers['authorization'];
  const token = authHeader && authHeader.split(' ')[1];

  if (!token) {
    return res.status(401).json({ error: 'Access token required' });
  }

  jwt.verify(token, process.env.JWT_SECRET, (err, user) => {
    if (err) {
      return res.status(403).json({ error: 'Invalid or expired token' });
    }
    req.user = user;
    next();
  });
};
```

### Python/Django Security Configuration

```python
# Django settings for secure API
from datetime import timedelta

# Security headers
SECURE_BROWSER_XSS_FILTER = True
SECURE_CONTENT_TYPE_NOSNIFF = True
X_FRAME_OPTIONS = 'DENY'
SECURE_HSTS_SECONDS = 31536000
SECURE_HSTS_INCLUDE_SUBDOMAINS = True
SECURE_HSTS_PRELOAD = True

# CORS configuration
CORS_ALLOWED_ORIGINS = [
    "https://trusted-frontend.com",
]
CORS_ALLOW_CREDENTIALS = True

# JWT configuration
SIMPLE_JWT = {
    'ACCESS_TOKEN_LIFETIME': timedelta(minutes=60),
    'REFRESH_TOKEN_LIFETIME': timedelta(days=7),
    'ROTATE_REFRESH_TOKENS': True,
    'BLACKLIST_AFTER_ROTATION': True,
    'ALGORITHM': 'HS256',
    'SIGNING_KEY': SECRET_KEY,
    'VERIFYING_KEY': None,
    'AUTH_HEADER_TYPES': ('Bearer',),
}

# Database security
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'OPTIONS': {
            'sslmode': 'require',
        },
    }
}
```

---

## ⚙️ Customization Guide

### Required Replacements
- `[FRAMEWORK]`: Your chosen framework (Flask, Express, Spring Boot, etc.)
- `[TECHNOLOGY]`: Specific technology stack
- `{id}`: Parameter placeholders
- `${VARIABLE}`: Environment variables

### Security Level Adjustments
- **Basic**: Standard security controls
- **Enhanced**: Additional compliance requirements
- **Enterprise**: Advanced threat protection
- **Government**: Maximum security hardening

---

## 🏷️ Tags

`#api-security` `#rest-api` `#graphql` `#oauth2` `#jwt` `#authentication` `#authorization` `#owasp` `#secure-coding` `#microservices`

---

## 📊 Effectiveness

- **Security**: ⭐⭐⭐⭐⭐ (Comprehensive OWASP compliance)
- **Performance**: ⭐⭐⭐⭐ (Optimized with security controls)
- **Maintainability**: ⭐⭐⭐⭐⭐ (Clean, documented code)
- **Scalability**: ⭐⭐⭐⭐ (Enterprise-ready architecture)

---

## ⚠️ Security Considerations

1. **Regular Security Audits**: Conduct periodic security assessments
2. **Dependency Management**: Keep all dependencies updated
3. **Environment Security**: Secure configuration management
4. **Monitoring**: Implement comprehensive security monitoring
5. **Incident Response**: Have security incident response procedures

---

## 📚 Related Prompts

- [Input Validation](./input-validation-security.md) - Comprehensive input sanitization
- [Authentication Systems](./authentication-systems.md) - User authentication patterns
- [Database Security](./database-security.md) - Secure data access patterns
- [Error Handling](./secure-error-handling.md) - Security-aware error management

---

*These prompts generate production-ready, secure APIs. Always review generated code and adapt to your specific security requirements.*