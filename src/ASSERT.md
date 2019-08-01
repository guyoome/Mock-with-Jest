# Matchers

Go back [home](../README.md/#mock-jest)

## Summary

- [ToBeCalled](#tobecalled)
- [ToBeCalledWith](#tobecalledwith)
- [lastCalledWith](#lastcalledwith)
- [toMatchSnapshot](#tomatchsnapshot)

## ToBeCalled

Assert to know if mock function as been called at least once

```javascript
expect(mockFunc).toBeCalled();
```

Another way to test it

```javascript
expect(mockFunc.mock.calls.length).toBeGreaterThan(0);
```

Assert to know if mock function as been called more than n times

```javascript
expect(mockFunc.mock.calls.length).toBeGreaterThan(n);
```

## ToBeCalledWith

Assert to know if mock function as been called with specific argument

```javascript
expect(mockFunc).toBeCalledWith(arg1, arg2);
```

Exemple :

```javascript
// declaration mockFunc
const mockResponse = () => {
  const res = {};
  res.status = jest
    .fn()
    .mockReturnValue(res)
    .mockName("res.status");
  return res;
};

//........//

describe("[CASE-X] - something to test", () => {
  it("should... ", async () => {
    // Arrange
    const res = mockResponse();
    //........//

    // Act
    try {
      await aRandomController(req, res);
    } catch (error) {
      //........//
    }

    // Assert
    expect(res.status).toBeCalledWith(500);
  });
});
```

## lastCalledWith

Assert to know if the last called of the mock function was with specific argument

```javascript
expect(mockFunc).lastCalledWith(arg1, arg2);
```

## toMatchSnapshot

```javascript
expect(mockFunc).toMatchSnapshot();
```
