# snippets

createNodeMock for ref mock

```javascript
const mockInputRef = {
  offsetWidth: 320
};

function createNodeMock(element) {
  if (element.type === "input") {
    return mockInputRef;
  }
  return element;
}

function renderComponent() {
  return renderer.create(<Foo />, {
    createNodeMock
  });
}
```

trigger hooks without anything fancy - use act

```javascript
// i.e.
import renderer, { act } from "react-test-renderer";

it("should do stuff", () => {
  act(() => {
    component = renderComponent();
  });

  const bar = component.root.findByProps({
    className: "bar"
  });

  expect(bar.something).toEqual("something");
});
```
