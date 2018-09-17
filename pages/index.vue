<script>
import Vue from 'vue';
import Raven from 'raven-js';
import RavenVue from 'raven-js/plugins/vue';

Raven
    .config('', {
      shouldSendCallback() {
        console.log('shouldSendCallback')
        return true;
      }
    })
    .addPlugin(RavenVue, Vue)
    .install();

import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  },
  errorCaptured(err, vm, info) {
    console.log(err, "errorCaptured!");
    return false;
  },
  render (_) {
    return <section>
    <div>
      test dayo
      <app-logo/>
    </div>
  </section>
  }
}
</script>
