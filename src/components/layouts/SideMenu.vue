<template>
    <div class="side-menu theme-dark" id="side-menu">
            <div class="user-menu theme-red clearfix">
                <div class="menu-logo">
                    <a id="sidebar-home-link"  href="https://rizk.com/en/casino-games"><img src="../../assets/rizk-logo-no-tm.svg" alt="casino" class="logo" width="126" height="41"></a>
                </div>
                <div class="sm-buttons">
                    <button href="/en/user/register" class="rizk-btn btn-yellow btn-wide">Sign up</button>
                    <button class="rizk-btn btn-black btn-wide">Log in</button>
                </div>
            </div>
            <div class="theme-dark main-navigation">
                <ul id="main-menu" class="menu main-menu">
                    <li><a   href="https://rizk.com/en/casino-games"><span class="icon games"></span><span class="item">Games</span></a></li>
                    <li><a href="https://rizk.com/en/sportsbook"><span class="icon sports"></span><span class="item">Sports</span><p class="badge-new">new</p></a></li>
                    <li><a href="https://rizk.com/en/casino/live-casino"><span class="icon live-casino"></span><span class="item">Live Casino</span></a></li>
                    <li><a href="https://rizk.com/en/casino/promotions"><span class="icon live-casino"></span><span class="item">Rizk Insider</span></a></li>
                    <li><a><span class="icon wor"></span><span class="item">Wheel of Rizk</span></a></li>
                    <li><a><span class="icon rizk-race"></span><span class="item">Rizk Race</span></a></li>
                    <li id="side-menu-live-chat" class="live-chat-link"><a class="live-chat-menu-item"><span class="icon live-chat"></span><span class="item">Customer Care</span></a></li>
                </ul>
            </div>
        </div>
</template>

<script>
export default {
    name: "SideMenu"
}
</script>

