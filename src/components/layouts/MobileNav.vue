<template>
      <div class="new-mobile-nav">
                <header id="topBar" class="top-bar">
                    <button id="signUp" class="rizk-btn btn-yellow btn-wide"  >Sign up</button><img src="../../assets/rizk-logo-no-tm.svg" alt="Rizk logo" width="110" height="25">
                    <button id="logIn" class="rizk-btn btn-black btn-wide"  >Log in</button>
                </header>
                <!-- Sidenav menu -->
                <div class="slider-filter" id="sliderFilter"></div>
                <nav id="rizkSidenav" class="sidenav">
                    <div class="top-bar-sidenav">
                        <div class="sidenav-logo">
                            <label   class="close-label" for="menu"><span class="close"></span></label><img src="../../assets/rizk-logo-no-tm.svg" alt="Rizk logo" width="110" height="30"></div>
                        <div class="sm-buttons">
                            <button class="rizk-btn btn-yellow btn-wide"  >Sign up</button>
                            <button class="rizk-btn btn-black btn-wide"  >Log in</button>
                        </div>
                    </div>
                    <div class="content-sidenav" id="linksSidenav"><a class="menu-item active-item" id="menu-item-casino"   href="https://rizk.com/en/casino-games"><i class="icon-casino" aria-hidden="true"></i><span>Games</span></a><a class="menu-item" id="menu-item-sportsbook" href="https://rizk.com/en/sportsbook"><i class="icon-sportsbook" aria-hidden="true"></i><span>Sports</span><p class="badge">new</p></a><a class="menu-item" id="menu-item-live-casino"  href="https://rizk.com/en/casino/live-casino"><i class="icon-live-casino" aria-hidden="true"></i><span>Live Casino</span></a>
                        <!-- div class="gray-separator"></div> --><a class="menu-item" id="menu-item-race"><i class="icon-rizk-race" aria-hidden="true"></i><span>Rizk Race</span></a>
                        <a href="https://rizk.com/en/wheel-of-rizk">
                            <div class="menu-item"><i class="icon-rizk-wheel" aria-hidden="true"></i><span>Wheel of Rizk</span></div>
                        </a>
                    </div>
                    <div class="bottom-bar-sidenav">
                        <div class="clock-sidenav"><span id="clock-sidenav">16:56</span></div>
                        <div id="side-menu-live-chat" class="live-chat-link chat-item"><a><i class="icon-live-chat" aria-hidden="true"></i><span>Customer Care</span></a></div>
                    </div>
                </nav>
                <div class="wrap">
                    <nav class="menu">
                        <div class="list" id="bottom-bar">
                            <div class="link-wrap"><a><i class="icon-menu" aria-hidden="true"></i><span>Menu</span></a><a id="menu-item-casino2"   href="https://rizk.com/en/casino-games" class="active-item"><i class="icon-casino" aria-hidden="true"></i><span>Games</span></a>
                                <a  ><img class="rizk-jewel-reward" src="../../assets/jewel_reward.svg" alt="Rizk reward"></a><a id="menu-item-insider-loggedout" href="https://rizk.com/en/casino/promotions"><i class="icon-rizk-insider" aria-hidden="true"></i><span>Rizk Insider</span></a><a id="menu-item-sportsbook2" href="https://rizk.com/en/sportsbook"><i class="icon-sportsbook" aria-hidden="true"></i><span>Sports</span></a></div>
                        </div>
                    </nav>
                </div>
            </div>
</template>

<script>
export default {
    name:"MobileNav"
}
</script>

