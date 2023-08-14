<template>
  <div class="min-h-screen flex relative lg:static surface-ground">
    <div id="app-sidebar-10"
      class="h-full lg:h-auto hidden lg:block flex-shrink-0 absolute lg:static left-0 top-0 z-1 border-right-1 surface-border w-full md:w-auto">
      <div class="flex h-full">
        <div class="flex flex-column h-full bg-indigo-900 flex-shrink-0 select-none">
          <div class="flex align-items-center justify-content-center flex-shrink-0" style="height:60px">
            <!-- <img src="images/blocks/logos/hyper-light.svg" alt="Image" height="30"> -->
          </div>
          <div class="overflow-y-auto mt-3">
            <ul class="list-none py-3 pl-2 pr-0 m-0">
              <li class="mb-2">
                <a v-ripple
                  class="flex align-items-center cursor-pointer py-3 pl-0 pr-2 justify-content-center hover:bg-indigo-600 text-indigo-100 hover:text-indigo-50 transition-duration-150 transition-colors p-ripple"
                  @click="activeTab = 0" :class="{ 'bg-indigo-500': activeTab === 0 }"
                  style="border-top-left-radius: 30px;border-bottom-left-radius: 30px;">
                  <i class="pi pi-home text-xl"></i>
                </a>
              </li>
              <li class="mb-2">
                <a v-ripple
                  class="flex align-items-center cursor-pointer py-3 pl-0 pr-2 justify-content-center hover:bg-indigo-600 text-indigo-100 hover:text-indigo-50 transition-duration-150 transition-colors p-ripple"
                  @click="activeTab = 1" :class="{ 'bg-indigo-500': activeTab === 1 }"
                  style="border-top-left-radius: 30px;border-bottom-left-radius: 30px;">
                  <i class="pi pi-bookmark text-xl"></i>
                </a>
              </li>
              <li class="mb-2">
                <a v-ripple
                  class="flex align-items-center cursor-pointer py-3 pl-0 pr-2 justify-content-center hover:bg-indigo-600 text-indigo-100 hover:text-indigo-50 transition-duration-150 transition-colors p-ripple"
                  @click="activeTab = 2" :class="{ 'bg-indigo-500': activeTab === 2 }"
                  style="border-top-left-radius: 30px;border-bottom-left-radius: 30px;">
                  <i class="pi pi-users text-xl"></i>
                </a>
              </li>
              <li class="mb-2">
                <a v-ripple
                  class="flex align-items-center cursor-pointer py-3 pl-0 pr-2 justify-content-center hover:bg-indigo-600 text-indigo-100 hover:text-indigo-50 transition-duration-150 transition-colors p-ripple"
                  @click="activeTab = 3" :class="{ 'bg-indigo-500': activeTab === 3 }"
                  style="border-top-left-radius: 30px;border-bottom-left-radius: 30px;">
                  <i class="pi pi-comments text-xl"></i>
                </a>
              </li>
              <li class="mb-2">
                <a v-ripple
                  class="flex align-items-center cursor-pointer py-3 pl-0 pr-2 justify-content-center hover:bg-indigo-600 text-indigo-100 hover:text-indigo-50 transition-duration-150 transition-colors p-ripple"
                  @click="activeTab = 4" :class="{ 'bg-indigo-500': activeTab === 4 }"
                  style="border-top-left-radius: 30px;border-bottom-left-radius: 30px;">
                  <i class="pi pi-calendar text-xl"></i>
                </a>
              </li>
              <li class="mb-2">
                <a v-ripple
                  class="flex align-items-center cursor-pointer py-3 pl-0 pr-2 justify-content-center hover:bg-indigo-600 text-indigo-100 hover:text-indigo-50 transition-duration-150 transition-colors p-ripple"
                  @click="activeTab = 5" :class="{ 'bg-indigo-500': activeTab === 5 }"
                  style="border-top-left-radius: 30px;border-bottom-left-radius: 30px;">
                  <i class="pi pi-cog text-xl"></i>
                </a>
              </li>
            </ul>
          </div>
          <div class="mt-auto">
            <hr class="mb-3 mx-2 border-top-1 border-none border-indigo-300" />
            <a v-ripple class="m-3 flex align-items-center cursor-pointer p-2 justify-content-center hover:bg-indigo-600 border-round text-300 hover:text-0
                        transition-duration-150 transition-colors p-ripple">
              <img src="images/blocks/avatars/circle/avatar-f-1.png" style="width: 24px; height: 24px" />
            </a>
          </div>
        </div>
        <div class="flex flex-column bg-indigo-500 p-4 overflow-y-auto flex-shrink-0 flex-grow-1 md:flex-grow-0"
          style="width:300px">
          <div class="justify-content-end mb-3 flex lg:hidden">
            <button icon="pi pi-times"
              class="cursor-pointer text-white appearance-none bg-transparent border-none inline-flex justify-content-center align-items-center border-circle hover:bg-indigo-600 transition-duration-150 transition-colors"
              style="width:2rem;height:2rem"
              v-styleclass="{ selector: '#app-sidebar-10', leaveToClass: 'hidden', leaveActiveClass: 'fadeoutleft' }">
              <i class="pi pi-times text-xl text-indigo-100"></i>
            </button>
          </div>
          <div class="border-round flex-auto">
            <div class="p-3 font-medium text-2xl text-white" :class="{ 'hidden': activeTab !== 0 }">Dashboard</div>
            <div class="p-3 font-medium text-2xl text-white" :class="{ 'hidden': activeTab !== 1 }">Bookmarks</div>
            <div class="p-3 font-medium text-2xl text-white" :class="{ 'hidden': activeTab !== 2 }">Team</div>
            <div class="p-3 font-medium text-2xl text-white" :class="{ 'hidden': activeTab !== 3 }">Messages</div>
            <div class="p-3 font-medium text-2xl text-white" :class="{ 'hidden': activeTab !== 4 }">Calendar</div>
            <div class="" :class="{ 'hidden': activeTab !== 5 }">
              <div class="p-3 font-medium text-2xl text-white mb-5">Settings</div>
              <ul class="list-none p-0 m-0 text-white">
                <li class="mb-3 flex align-items-start bg-indigo-700 p-3" style="border-radius: 12px">
                  <i class="pi pi-user text-xl mr-3 "></i>
                  <div class="flex flex-column">
                    <span>Account</span>
                    <p class="mt-2 mb-0 line-height-3 text-indigo-200">Accumsan sit amet nulla facilisi morbi tempus
                      iaculis.</p>
                  </div>
                </li>
                <li class="mb-3 flex align-items-start p-3" style="border-radius: 12px">
                  <i class="pi pi-inbox text-xl mr-3 "></i>
                  <div class="flex flex-column">
                    <span>Inbox</span>
                    <p class="mt-2 mb-0 line-height-3 text-indigo-200">Condimentum vitae sapien pellentesque habitant.</p>
                  </div>
                </li>
                <li class="mb-3 flex align-items-start p-3" style="border-radius: 12px">
                  <i class="pi pi-credit-card text-xl mr-3 "></i>
                  <div class="flex flex-column">
                    <span>Sales</span>
                    <p class="mt-2 mb-0 line-height-3 text-indigo-200">Egestas integer eget aliquet nibh praesent
                      tristique.</p>
                  </div>
                </li>
                <li class="mb-3 flex align-items-start p-3" style="border-radius: 12px">
                  <i class="pi pi-lock text-xl mr-3 "></i>
                  <div class="flex flex-column">
                    <span>Privacy</span>
                    <p class="mt-2 mb-0 line-height-3 text-indigo-200">In ante metus dictum at tempor commodo ullamcorper
                      a lacus.</p>
                  </div>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="min-h-screen flex flex-column relative flex-auto">
      
    <div class="flex flex-column flex-auto min-h-screen">
      <Map/>
    </div>
  </div>
</div>
</template>

<script>
import Map from './Map.vue'
export default {
  components: { Map },
  data() {
    return{
      activeTab: 0
    }
  }
}
</script>

<style></style>