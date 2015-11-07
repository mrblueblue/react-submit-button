# react-submit-button

A Stateless Function Component for your submit button needs.

``` javascript
import React from 'react';
import SubmitButton from 'react-submit-button';

const SubmitButtonContainer = ({status, asyncAction}) => (
  <SubmitButton
    submissionStatus={status}
    handleSubmit={asyncAction}
    texts={{
      default: 'Submit',
      loading: 'Submitting...',
      success: 'Submitted',
      errror: 'Try Again'
    }}
  />
)

```

`status` is basically state that is passed down as a prop. It should conform to either `loading`, `success`, `error`. Its default or ready state can be any string.

`asyncAction` is an asynchronous action (most likely a promise chain) that updates the `status` state depending on the async action's ongoingness, success, or failure. For instance, in the parent Component of `<SubmitButton/>`, one might find a promise chain like this:

```javascript

this.setState({status: 'loading'});
fetch(my.api.endpoit)
  .then((data) => {
    doSomething(data);
    this.setState({status: 'success'});
  })
  .catch((error) => {
    doSomethingElse(error);
    this.setState({status: 'error'})
  });

```