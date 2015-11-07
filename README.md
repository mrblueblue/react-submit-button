# react-submit-button

A Stateless Function Component for your submit button needs.

```
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

Status is basically state that passed down as props. It should conform to either `loading`, `success`, `error`. Its default or ready state can be any string.