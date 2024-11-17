<script setup lang="ts">
defineProps({
  animated: {
    type: Boolean,
    default: true,
  },
});
</script>

<template>
  <aside class="waterfall-bg" :class="{ animated: animated }">
    <div class="waterfall">
      <svg viewBox="0 0 349 387" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <rect x="120.095" y="47.665" width="141.611" height="297.335" fill="#59B7D4" class="waterfall-stream" />
        <rect x="120.096" y="24.2297" width="141.611" height="83.6565" fill="#DAF1FB" />
        <g class="waterfall-top">
          <rect x="120.096" y="66.5288" width="35.4028" height="93.9961" rx="17.7014" fill="#DAF1FB"
            class="waterfall-top-primary" />
          <rect x="208.603" y="48.6689" width="17.7014" height="93.9961" rx="8.85069" fill="#DAF1FB"
            class="waterfall-top-primary" />
          <rect x="173.2" y="38.3296" width="17.7014" height="93.9961" rx="8.85069" fill="#DAF1FB"
            class="waterfall-top-primary" />
          <rect x="244.005" y="30.8105" width="17.7014" height="93.9961" rx="8.85069" fill="#DAF1FB"
            class="waterfall-top-primary" />
          <rect x="226.304" y="95.6663" width="17.7014" height="93.9961" rx="8.85069" fill="#59B7D3"
            class="waterfall-top-mask" />
          <rect x="190.902" y="85.3267" width="17.7014" height="93.9961" rx="8.85069" fill="#59B7D3"
            class="waterfall-top-mask" />
          <rect x="155.499" y="95.6663" width="17.7014" height="93.9961" rx="8.85069" fill="#59B7D3"
            class="waterfall-top-mask" />
        </g>

        <g class="waterfall-foam">
          <circle cx="138.5" cy="326.5" r="20.5" fill="#DAF1FB" class="waterfall-foam-1" />
          <circle cx="174" cy="328" r="26" fill="#DAF1FB" class="waterfall-foam-1" />
          <circle cx="210.5" cy="334.5" r="23.5" fill="#DAF1FB" class="waterfall-foam-1" />
          <circle cx="246" cy="326" r="18" fill="#DAF1FB" class="waterfall-foam-1" />
          <circle cx="133" cy="324" r="17" fill="#DAF1FB" class="waterfall-foam-2" />
          <circle cx="174" cy="325" r="23" fill="#DAF1FB" class="waterfall-foam-2" />
          <circle cx="211" cy="329" r="23" fill="#DAF1FB" class="waterfall-foam-2" />
          <circle cx="246" cy="333" r="23" fill="#DAF1FB" class="waterfall-foam-2" />

          <circle cx="138.5" cy="326.5" r="20" fill="#DAF1FB" class="waterfall-foam-3" />
          <circle cx="174" cy="328" r="26" fill="#DAF1FB" class="waterfall-foam-3" />
          <circle cx="211" cy="329" r="24" fill="#DAF1FB" class="waterfall-foam-3" />
          <circle cx="246" cy="333" r="18" fill="#DAF1FB" class="waterfall-foam-3" />
        </g>

        <g class="splashes">
          <circle cx="147.045" cy="282.045" r="7.04465" fill="#DAF1FB" />
          <circle cx="203.681" cy="283.681" r="5.68125" fill="#DAF1FB" />
          <circle cx="254.021" cy="282.044" r="7.49911" fill="#DAF1FB" />
          <circle cx="269.136" cy="300.136" r="6.13572" fill="#DAF1FB" />
          <circle cx="119.136" cy="293.587" r="6.13572" fill="#DAF1FB" />
          <circle cx="124.681" cy="271.681" r="5.68125" fill="#DAF1FB" />
        </g>
      </svg>
    </div>
  </aside>
</template>

<style scoped lang="scss">
@use 'sass:math';
// animation below made by @Craaftx

$wooble-duration: 0.8s;
$grow-duration: 0.6s;
$jump-duration: 1s;
$splashes-duration: 1s;

.waterfall-bg {
  position: absolute;
  right: -120px;
  top: -50px;
  width: 40rem;

  &.animated .waterfall {
    &-top-primary {
      animation: wooble $wooble-duration ease-in-out alternate infinite;
    }

    &-top-mask {
      animation: wooble $wooble-duration ease-in-out alternate infinite;
    }

    @for $i from 1 through 7 {
      .waterfall-top:nth-child(#{$i}) {
        animation-delay: math.random(300) + ms;
      }
    }

    .waterfall-foam-1 {
      animation: jump-left $jump-duration ease-in-out alternate infinite;
    }

    .waterfall-foam-2 {
      animation: jump-right $jump-duration ease-in-out alternate infinite;
    }

    .waterfall-foam-3 {
      animation: grow $grow-duration ease-in-out alternate infinite;
    }

    @for $i from 1 through 12 {
      .waterfall-foam:nth-child(#{$i}) {
        animation-delay: math.random(400) + ms;
      }
    }

    .splashes {
      circle {
        animation: jump $splashes-duration ease-in-out alternate infinite;
      }

      @for $i from 1 through 7 {
        circle:nth-child(#{$i}) {
          animation-delay: math.random(1200) + ms;
        }
      }
    }
  }
}

@keyframes wooble {
  0% {
    transform: translateY(0);
  }

  100% {
    transform: translateY(3px);
  }
}

@keyframes grow {
  0% {
    transform: translate(0px, 0px);
  }

  100% {
    transform: translate(0px, -10px);
  }
}

@keyframes jump-right {
  0% {
    transform: translate(0px, -10px);
  }

  50% {
    transform: translate(-20px, 10px);
  }

  100% {
    transform: translate(0px, -5px);
  }
}

@keyframes jump-left {
  0% {
    transform: translate(0px, -10px);
  }

  50% {
    transform: translate(20px, 10px);
  }

  100% {
    transform: translate(0px, -5px);
  }
}

@keyframes jump {
  0% {
    transform: translateY(-10px);
  }

  100% {
    transform: translateY(50px);
  }
}
</style>
