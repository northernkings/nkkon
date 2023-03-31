<script lang="ts" setup>
import EditorialSection from "~/components/EditorialSection";
import VButton from "~/components/VButton";
import LayoutBase from "~/layouts/LayoutBase";
import Separator from "~/components/Separator";
import { reactive } from "vue";

defineProps({
  step: Number,
});

const formValues = reactive({
  name: "",
  email: "",
  fridayEvening: "",
  saturday: "",
  saturdayEvening: "",
  sunday: "",
  kowDoublesPartner: "",
});
</script>

<template>
  <LayoutBase :compact-header="true">
    <EditorialSection
      title="Step 1: Attendee Details"
      :variants="['single']"
      title-as="h1"
      v-if="step === 1"
    >
      <p>Registration is split into two steps 1) Attendee Details 2) Payment.</p>
      <p>
        If you're planning on registering for multiple attendees, please complete a registration for
        each player individually.
      </p>
      <p>
        Tickets are priced at <strong>&pound;55</strong>, include a proper lunch on Saturday and
        Sunday.
      </p>

      <Separator :compact="true" />

      <form
        action="/register-step-2/"
        name="nkkRegistration2023"
        method="POST"
        netlify-honeypot="bot-field"
        data-netlify-recaptcha="true"
        data-netlify="true"
        class="c-form l-flow-fat"
      >
        <div class="u-hidden">
          <label for="bot-field">Ignore this field if you are human</label>
          <input id="bot-field" name="bot-field" />
          <input type="hidden" name="subject" value="Northern KING KON 2023 - Registration" />
          <input type="hidden" name="form-name" value="nkkRegistration2023" />
        </div>

        <h3>Attendee details</h3>

        <div class="c-form__group">
          <label for="name">Attendee's Full Name</label>
          <input id="name" name="name" type="text" required placeholder="e.g. Ronnie Renton" />
        </div>

        <div class="c-form__group">
          <label for="email">Contact Email</label>
          <p>
            <small>
              Note: we will only use this email address to communicate about the event.
            </small>
          </p>
          <input
            id="email"
            name="email"
            type="email"
            required
            placeholder="e.g. ronnie@example.com"
          />
        </div>

        <h3>Please select individual events</h3>
        <p>
          <small>
            Note: these selections <strong>do not</strong> lock the attendee into any individual
            event. Changes can be made at any point by getting in touch withe event organisers.
            Though, giving us indicative numbers helps with our organisation.
          </small>
        </p>

        <div class="c-form__group l-flow">
          <div class="c-form__group">
            <label for="fridayEvening">Friday (Evening)</label>
            <select
              id="fridayEvening"
              name="fridayEvening"
              required
              v-model="formValues.fridayEvening"
            >
              <option value="" disabled selected>Select an option</option>
              <option value="Firefight (500 points)">Firefight (500 points)</option>
              <option value="Kings of War Ambush (800 points)">
                Kings of War Ambush (800 points)
              </option>
              <option value="Open Gaming">
                Open Gaming (e.g. board games, practice games etc.)
              </option>
              <option value="None/Unsure">None/Unsure</option>
            </select>
          </div>
          <div class="c-form__group">
            <label for="saturdayDay">Saturday (Day)</label>
            <select id="saturdayDay" name="saturdayDay" required v-model="formValues.saturday">
              <option value="" disabled selected>Select an option</option>
              <option value="Firefight Singles (1500 points)">
                Firefight Singles (1500 points)
              </option>
              <option value="Kings of War Singles (2300 points)">
                Kings of War Singles (2300 points)
              </option>
              <option value="None/Unsure">None/Unsure</option>
            </select>
          </div>
          <div class="c-form__group">
            <label for="saturdayEvening">Saturday (Evening)</label>
            <select
              id="saturdayEvening"
              name="saturdayEvening"
              required
              v-model="formValues.saturdayEvening"
            >
              <option value="" disabled selected>Select an option</option>
              <option value="Firefight Big Tank Battle">Firefight "Big Tank Battle"</option>
              <option value="Open Gaming">
                Open Gaming (e.g. board games, practice games etc.)
              </option>
              <option value="None/Unsure">None/Unsure</option>
            </select>
          </div>
          <div class="l-flow">
            <div class="c-form__group">
              <label for="sundayDay">Sunday (Day)</label>
              <p>
                <small>
                  Note: you do not need to decide on a partner to register for the Kings of War
                  Doubles. We will find you a partner if nessessary.
                </small>
              </p>
              <select id="sundayDay" name="sundayDay" required v-model="formValues.sunday">
                <option value="" disabled selected>Select an option</option>
                <option value="Kings of War Doubles">Kings of War Doubles</option>
                <option value="Deadzone">Deadzone</option>
                <option value="Armada">Armada</option>
                <option value="None/Unsure">None/Unsure</option>
              </select>
            </div>
            <div class="c-form__group" v-show="formValues.sunday === 'Kings of War Doubles'">
              <label for="kowDoublesPartner">Kings of War doubles partner name (Optional)</label>
              <input
                id="kowDoublesPartner"
                name="kowDoublesPartner"
                type="text"
                required
                placeholder="e.g. Nick Williams"
                v-model="formValues.kowDoublesPartner"
              />
            </div>
          </div>
        </div>

        <div class="c-form__group" data-netlify-recaptcha="true"></div>

        <VButton type="submit" :variants="['decorative', 'invert']">
          Submit and Continue to Payment (&pound;55)
        </VButton>
      </form>
    </EditorialSection>
    <EditorialSection
      title="Step 2: Payment"
      :variants="['single']"
      title-as="h1"
      v-if="step === 2"
    >
      <p>
        Thank you for submitting your attendee details, to complete the registration we require
        payment. The below button will redirect you to PayPal.
      </p>
      <p>
        Due to the fact not all people use the same name and email for their PayPal account, when
        paying, it is important that you also
        <strong>enter the attendee's full name into the notes field</strong> for us to correctly
        match your payment to your registration name.
      </p>
      <VButton
        class="c-header__book-now__action"
        href="https://www.paypal.com/paypalme/northernkings/55"
        :variants="['invert', 'decorative', 'lg']"
      >
        Complete Registration with PayPal
      </VButton>
      <p><small>Note: Any registration without a matching payment will be disregarded.</small></p>
    </EditorialSection>
  </LayoutBase>
</template>

<style>
@import "~/assets/styles/resources.css";

label {
  display: block;
}

small {
  display: block;
  line-height: 1.2;
  margin-top: var(--space-x-1);
}

input[type="text"],
input[type="email"],
select {
  display: block;
  width: 100%;
  margin-top: var(--space-x-2);
  padding: var(--space-y-3) var(--space-x-3);
  border-radius: 0;
  border: 2px solid var(--color-brand-fuscous);
}

option:disabled {
  color: #777
}

::placeholder {
  color: #777;
}

fieldset {
  all: unset;
  padding: 0;
  border: 0;
  width: 100%;
}

fieldset > legend + * {
  padding-top: var(--space-y-3);
}
</style>
