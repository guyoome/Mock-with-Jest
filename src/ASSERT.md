# ASSERT

## ToBeCalled

```javascript
expect(mockFunc).toBeCalled();
```

```javascript
expect(mockFunc.mock.calls.length).toBeGreaterThan(0);
```

```javascript
expect(mockFunc.mock.calls.length).toBeGreaterThan(n);
```

## ToBeCalledWith

```javascript
expect(mockFunc).toBeCalledWith(arg1, arg2);
```

```javascript
expect(mockFunc).lastCalledWith(arg1, arg2);
```

## toMatchSnapshot

```javascript
expect(mockFunc).toMatchSnapshot();
```
