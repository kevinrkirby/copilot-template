# Python Testing Instructions

This file contains specific instructions for GitHub Copilot when working with Python testing code.

## Testing Framework

- Use pytest as the primary testing framework
- Follow pytest conventions and best practices
- Use descriptive test function names that explain what is being tested
- Organize tests in logical modules and classes

## Test Structure

- Follow the Arrange-Act-Assert (AAA) pattern
- Use fixtures for common setup and teardown
- Group related tests in classes
- Use parametrize for testing multiple scenarios

## Test Coverage

- Aim for high test coverage but focus on quality over quantity
- Test both positive and negative cases
- Include edge cases and boundary conditions
- Test error handling and exception cases

## Mocking and Fixtures

- Use unittest.mock or pytest-mock for mocking dependencies
- Create reusable fixtures for common test data
- Mock external services and APIs appropriately
- Use factory patterns for creating test objects

## Assertions

- Use clear and specific assertions
- Prefer pytest's assert statements over unittest assertions
- Use pytest.raises() for testing exceptions
- Include meaningful error messages in assertions

## Test Organization

```
tests/
├── conftest.py          # Shared fixtures and configuration
├── unit/                # Unit tests
│   ├── test_models.py
│   └── test_utils.py
├── integration/         # Integration tests
│   └── test_api.py
└── fixtures/            # Test data and fixtures
    └── sample_data.py
```

## Best Practices

- Keep tests isolated and independent
- Use descriptive test names that explain the scenario
- Test one thing at a time
- Make tests fast and reliable
- Use type hints in test code
- Follow PEP 8 style guidelines
- Clean up resources in teardown methods

## Example Test Structure

```python
import pytest
from unittest.mock import Mock, patch

class TestUserService:
    def test_create_user_with_valid_data_should_return_user_id(self):
        # Arrange
        user_data = {"name": "John", "email": "john@example.com"}
        
        # Act
        result = user_service.create_user(user_data)
        
        # Assert
        assert result is not None
        assert isinstance(result, int)

    def test_create_user_with_invalid_email_should_raise_validation_error(self):
        # Arrange
        user_data = {"name": "John", "email": "invalid-email"}
        
        # Act & Assert
        with pytest.raises(ValidationError):
            user_service.create_user(user_data)
```