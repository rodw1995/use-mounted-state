# use-mounted-state
React hook to check mounted state

## Install

```sh
yarn add @rodw95/use-mounted-state

// or

npm install @rodw95/use-mounted-state
```

## Example

```js
import useIsMounted from '@rodw95/use-mounted-state';
import React, { useCallback, useState } from 'react';

export default () => {
  const isMounted = useIsMounted();
  const [state, setState] = useState(null);

  const doFetch = useCallback(async () => {
    const result = await fetchAsync();
    if (isMounted()) {
      // Only set state if still mounted
      setState(result);
    }
  });

  return (
    // ...
  );
};
```

## License

[MIT](LICENSE)
