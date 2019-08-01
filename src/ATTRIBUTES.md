# Attributes

Go back [home](../README.md/#mock-jest)

## Summary

- [\_isMockFunction](#ismockfunction)
- [getMockImplementation](#getmockimplementation)
- [mock](#mock)
  - [calls](#calls)
  - [instances](#instances)
  - [invocationCallOrder](#invocationcallorder)
  - [results](#results)
- [mockClear](#mockclear)
- [mockReset](#mockreset)
- [mockRestore](#mockrestore)
- [mockReturnValueOnce](#mockreturnvalueonce)
- [mockResolvedValueOnce](#mockresolvedvalueonce)
- [mockRejectedValueOnce](#mockrejectedvalueonce)
- [mockReturnValue](#mockreturnvalue)
- [mockResolvedValue](#mockresolvedvalue)
- [mockRejectedValue](#mockrejectedvalue)
- [mockImplementationOnce](#mockimplementationonce)
- [mockImplementation](#mockimplementation)
- [mockReturnThis](#mockreturnthis)
- [mockName](#mockname)
- [getMockName](#getmockname)

## \_isMockFunction

```javascript
const myMock = jest.fn();
myMock._isMockFunction;
```

> return a Boolean

## getMockImplementation

```javascript
() => this._ensureMockConfig(f).mockImpl;
```

## mock

### calls

```javascript
typeof myMock.mock.calls === Array();
```

### instances

```javascript
typeof myMock.mock.instances === Array();
```

### invocationCallOrder

```javascript
typeof myMock.mock.invocationCallOrder === Array();
```

### results

```javascript
typeof myMock.mock.results === Array();
```

## mockClear

```javascript
() => {
  this._mockState.delete(f);
  return f;
};
```

## mockReset

```javascript
() => {
  f.mockClear();

  this._mockConfigRegistry.delete(f);

  return f;
};
```

## mockRestore

```javascript
() => {
  f.mockReset();

  return restore ? restore() : undefined;
};
```

## mockReturnValueOnce

```javascript
value => {
  // next function call will return this value or default
  return value;
  const mockConfig = this._ensureMockConfig(f);

  mockConfig.specificReturnValues.push(value);
  return f;
};
```

## mockResolvedValueOnce

```javascript
value => f.mockImplementationOnce(() => Promise.resolve(value));
```

## mockRejectedValueOnce

```javascript
value => f.mockImplementationOnce(() => Promise.reject(value));
```

## mockReturnValue

```javascript
value => {
  // next function call will return specified return value or this one
  const mockConfig = this._ensureMockConfig(f);

  mockConfig.isReturnValueLastSet = true;
  mockConfig.defaultReturnValue = value;
  return f;
};
```

## mockResolvedValue

```javascript
value => f.mockImplementation(() => Promise.resolve(value));
```

## mockRejectedValue

```javascript
value => f.mockImplementation(() => Promise.reject(value));
```

## mockImplementationOnce

```javascript
fn => {
  // next function call will use this mock implementation return value
  // or default mock implementation return value
  const mockConfig = this._ensureMockConfig(f);

  mockConfig.isReturnValueLastSet = false;
  mockConfig.specificMockImpls.push(fn);
  return f;
};
```

## mockImplementation

```javascript
fn => {
  // next function call will use mock implementation return value
  const mockConfig = this._ensureMockConfig(f);

  mockConfig.isReturnValueLastSet = false;
  mockConfig.defaultReturnValue = undefined;
  mockConfig.mockImpl = fn;
  return f;
};
```

## mockReturnThis

```javascript
() =>
  f.mockImplementation(function() {
    return this;
  });
```

## mockName

```javascript
name => {
  if (name) {
    const mockConfig = this._ensureMockConfig(f);

    mockConfig.mockName = name;
  }

  return f;
};
```

## getMockName

```javascript
() => {
  const mockConfig = this._ensureMockConfig(f);

  return mockConfig.mockName || "jest.fn()";
};
```
