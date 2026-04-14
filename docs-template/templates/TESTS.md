# Test Suite

**Last updated:** <!-- YYYY-MM-DD -->
**Runner:** <!-- e.g., Vitest + jsdom, Jest, pytest -->
**Command:** <!-- e.g., `bun run test`, `npm test`, `pytest` -->

---

## Active Tests

### Business Logic Unit Tests

| File | Feature | Tests | What it covers |
|------|---------|-------|----------------|
| <!-- path --> | <!-- feature --> | <!-- count --> | <!-- brief description --> |

### Storage / Data Persistence

| File | Feature | Tests | What it covers |
|------|---------|-------|----------------|
| <!-- path --> | <!-- feature --> | <!-- count --> | <!-- brief description --> |

### API & Error Handling

| File | Feature | Tests | What it covers |
|------|---------|-------|----------------|
| <!-- path --> | <!-- feature --> | <!-- count --> | <!-- brief description --> |

### Security

| File | Feature | Tests | What it covers |
|------|---------|-------|----------------|
| <!-- path --> | <!-- feature --> | <!-- count --> | <!-- brief description --> |

---

## Skipped Tests

<!-- Tests that exist but are disabled. Document WHY each is skipped so they don't rot. -->

| File | Reason | Re-enable when |
|------|--------|----------------|
| <!-- path --> | <!-- why skipped --> | <!-- condition to re-enable --> |

## Future Tests

<!-- Tests that should exist but haven't been written yet. Organized by category. -->

### Ready to Write
<!-- Tests where the code exists and just needs test coverage -->

### Blocked
<!-- Tests that need infrastructure or features that don't exist yet -->

### E2E
<!-- End-to-end tests for critical user flows -->

---

## Conventions

- **Location**: <!-- e.g., `src/test/` for unit, `tests/e2e/` for E2E -->
- **Naming**: <!-- e.g., `<feature>-<domain>.test.ts` -->
- **Mocks**: <!-- e.g., "Use vi.fn() for unit tests, MSW for API integration tests" -->
- **Skip pattern**: <!-- e.g., `describe.skip` with a comment explaining why -->
- **State cleanup**: <!-- e.g., "Clear localStorage in beforeEach" -->
- **API mocking**: <!-- e.g., "MSW handlers in src/test/mocks/" -->

## Dependencies

| Package | Purpose |
|---------|---------|
| <!-- e.g., vitest --> | <!-- Test runner --> |
| <!-- e.g., @testing-library/react --> | <!-- Component testing utilities --> |
| <!-- e.g., msw --> | <!-- API mocking --> |
| <!-- e.g., jsdom --> | <!-- DOM environment --> |
