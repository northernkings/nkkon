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
        Tickets are priced at <strong>&pound;55</strong>, include a proper lunch on both days and a
        planned evening social.
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
          <h4>fridayEvening (Evening)</h4>
          <div class="c-form__group l-flow-slim">
            <label for="fridayEveningFirefight">
              <input
                id="fridayEveningFirefight"
                name="fridayEvening"
                type="radio"
                value="Firefight (500 points)"
                required
                v-model="formValues.fridayEvening"
              />
              Firefight (500 points)
            </label>
            <label for="fridayEveningKowAmbush">
              <input
                id="fridayEveningKowAmbush"
                name="fridayEvening"
                type="radio"
                value="Kings of War Ambush (800 points)"
                required
                v-model="formValues.fridayEvening"
              />
              Kings of War Ambush (800 points)
            </label>
            <label for="fridayEveningOpen">
              <input
                id="fridayEveningOpen"
                name="fridayEvening"
                type="radio"
                value="Open Gaming"
                required
                v-model="formValues.fridayEvening"
              />
              Open Gaming (e.g. board games, practice games etc.)
            </label>
            <label for="fridayEveningNone">
              <input
                id="fridayEveningNone"
                name="fridayEvening"
                type="radio"
                value="None/Unsure"
                required
                v-model="formValues.fridayEvening"
              />
              None/Unsure
            </label>
          </div>

          <h4>Saturday (Day)</h4>
          <div class="c-form__group l-flow-slim">
            <label for="saturdayFirefight">
              <input
                id="saturdayFirefight"
                name="saturday"
                type="radio"
                value="Firefight Singles (1500 points)"
                required
                v-model="formValues.saturday"
              />
              Firefight Singles (1500 points)
            </label>
            <label for="saturdayKow">
              <input
                id="saturdayKow"
                name="saturday"
                type="radio"
                value="Kings of War Singles (2300 points)"
                required
                v-model="formValues.saturday"
              />
              Kings of War Singles (2300 points)
            </label>
            <label for="saturdayNone">
              <input
                id="saturdayNone"
                name="saturday"
                type="radio"
                value="None/Unsure"
                required
                v-model="formValues.saturday"
              />
              None/Unsure
            </label>
          </div>

          <h4>Saturday (Evening)</h4>
          <div class="c-form__group l-flow-slim">
            <label for="saturdayEveningFirefight">
              <input
                id="saturdayEveningFirefight"
                name="saturdayEvening"
                type="radio"
                value="Firefight Big Tank Battle"
                required
                v-model="formValues.saturdayEvening"
              />
              Firefight "Big Tank Battle"
            </label>
            <label for="saturdayEveningOpen">
              <input
                id="saturdayEveningOpen"
                name="saturdayEvening"
                type="radio"
                value="Open Gaming"
                required
                v-model="formValues.saturdayEvening"
              />
              Open Gaming (e.g. board games, practice games etc.)
            </label>
            <label for="saturdayEveningNone">
              <input
                id="saturdayEveningNone"
                name="saturdayEvening"
                type="radio"
                value="None/Unsure"
                required
                v-model="formValues.saturdayEvening"
              />
              None/Unsure
            </label>
          </div>

          <h4>Sunday (Day)</h4>
          <div class="c-form__group l-flow-slim">
            <p>
              <small>
                Note: you do not need to decide on a partner to register for the Kings of War
                Doubles. We will find you a partner if nessessary.
              </small>
            </p>
            <label for="sundayKow">
              <input
                id="sundayKow"
                name="sunday"
                type="radio"
                value="Kings of War Doubles"
                v-model="formValues.sunday"
              />
              Kings of War Doubles
            </label>
            <label for="sundayDeadzone">
              <input
                id="sundayDeadzone"
                name="sunday"
                type="radio"
                value="Deadzone"
                v-model="formValues.sunday"
              />
              Deadzone
            </label>
            <label for="sundayArmada">
              <input
                id="sundayArmada"
                name="sunday"
                type="radio"
                value="Armada"
                v-model="formValues.sunday"
              />
              Armada
            </label>
            <label for="sundayNone">
              <input
                id="sundayNone"
                name="sunday"
                type="radio"
                value="None/Unsure"
                v-model="formValues.sunday"
              />
              None/Unsure
            </label>
            <div class="c-form__group" v-if="formValues.sunday === 'Kings of War Doubles'">
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
input[type="email"] {
  width: 100%;
  margin-top: var(--space-x-2);
  padding: var(--space-y-3) var(--space-x-3);
  border-radius: 0;
  border: 2px solid var(--color-brand-fuscous);
}
</style>
