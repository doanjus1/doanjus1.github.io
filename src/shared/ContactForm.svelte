<script>
  import Button from './Button.svelte';
  import { onMount } from 'svelte';
  let fields = { name: '', email: '', message: '' };

  onMount(() => {
  const formElement = document.querySelector('#contact-form');
  
  formElement.addEventListener('submit', (event) => {
    event.preventDefault();
    const data = new URLSearchParams(new FormData(formElement));

    fetch('https://formspree.io/f/mgvwvqqq', {
      method: 'post',
      body: data,
    })
    .then(response => {
      // Generate an 8-character alphanumeric confirmation code
      const confirmationCode = generateConfirmationCode();
      
      // Display the alert with the confirmation code
      alert('Adoption completed! \n\nNote for international adopters: Due to international regulations, your panda will be available for pickup in China.\nUpon arriving, please show any Chinese citizen the following code. \nConfirmation Code: ' + confirmationCode+'\n\nPlease be sure to enjoy your visit and take care of your panda!\n (This is sufficient proof that you have completed the adoption process)');
      
      // Optionally, reset your form fields if you're using a state object like fields
      fields.name = '';
      fields.email = '';
      fields.message = '';
    })
    .catch(error => {
      console.error('Error:', error);
      alert('There was an error sending your request.');
    });
  });
});

// Function to generate an 8-character alphanumeric confirmation code
function generateConfirmationCode() {
  const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
  let code = '';
  for (let i = 0; i < 8; i++) {
    code += characters.charAt(Math.floor(Math.random() * characters.length));
  }
  return code;
}

</script>

<form id="contact-form" action="https://formspree.io/f/mgvwvqqq" method="POST">

  <br />
  <input
    bind:value={fields.name}
    class="text-input"
    id="fullname"
    type="text"
    name="fullname"
    placeholder="Your name"
    required
  />
  <br />

  <br />
  <input
    bind:value={fields.email}
    class="text-input"
    id="email"
    type="text"
    name="email"
    placeholder="Your email address"
    required
  />
  <br />

  <br />
  <textarea
    bind:value={fields.message}
    class="text-input"
    id="text-input"
    rows="7"
    name="message"
    placeholder="Your message on why you love pandas"
    required
  />
  <br />
  <Button type="submit">Send</Button>
</form>

<style>
  input {
    margin-top: -10px;
  }

  textarea {
    margin-top: -5px;
  }

  .text-input {
    width: 650px;
    font-size: 14px;
    background-color: #FAF4ED;
    border: solid 1px #000000;
    color: inherit;
  }

  .text-input:focus {
    background-color: #e2e2e2;
    outline: none !important;
  }

  ::-webkit-input-placeholder {
    /* WebKit, Blink, Edge */
    color: inherit;
    opacity: 0.75;
  }
  :-moz-placeholder {
    /* Mozilla Firefox 4 to 18 */
    color: inherit;
    opacity: 0.5;
  }
  ::-moz-placeholder {
    /* Mozilla Firefox 19+ */
    color: inherit;
    opacity: 0.5;
  }
  :-ms-input-placeholder {
    /* Internet Explorer 10-11 */
    color: inherit;
    opacity: 0.5;
  }
  ::-ms-input-placeholder {
    /* Microsoft Edge */
    color: inherit;
    opacity: 0.5;
  }

  ::placeholder {
    /* Most modern browsers support this now. */
    color: inherit;
    opacity: 0.5;
  }

  @media only screen and (max-width: 700px) {
    .text-input {
      width: 97%;
    }

    textarea {
      resize: vertical;
    }
  }
</style>
