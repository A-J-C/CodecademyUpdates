This code adds more information to any CC profile; specifically: Best Streak and Points Today

Run this code from the console to get it to work:

    var profile = function () {
        if ($("form").attr("action") == "/admin/user_present?method=post") {
            $.getJSON('/api/v1/users' + window.location.pathname, function (d) {
                CCDATA.user = d
            }).done(function () {
                $("article.fit-full.color-scheme--darkgrey").after('<article class="fit-full color-scheme--darkgrey"><div class="fit-fixed"><div class="grid-row profile-time" style=" text-align: center;"><div class="grid-col-3 grid-col--align-center" style=" float: none;display: inline-block;"><h3 class="padding-right--quarter">' + CCDATA.user.points_today + '</h3><small>points today</small></div><div class="grid-col-3 grid-col--align-center" style=" float: none;display: inline-block;"><h3 class="padding-right--quarter">' + CCDATA.user.streak_hash.max_count + '</h3><small>day best streak</small></div></div></div></article>');
            });
        }
    }
    
    var script = document.createElement("script");
    script.textContent = "(" + profile.toString() + "())";
    document.documentElement.appendChild(script);


To instead use it as a **bookmarklet** save this as a bookmark:

    javascript:(function(){if($("form").attr("action")=="/admin/user_present?method=post"){$.getJSON('/api/v1/users'+window.location.pathname,function(d){CCDATA.user=d}).done(function(){$("article.fit-full.color-scheme--darkgrey").after('<article%20class="fit-full%20color-scheme--darkgrey"><div%20class="fit-fixed"><div%20class="grid-row%20profile-time"%20style="%20text-align:%20center;"><div%20class="grid-col-3%20grid-col--align-center"%20style="%20float:%20none;display:%20inline-block;"><h3%20class="padding-right--quarter">'+CCDATA.user.points_today+'</h3><small>points%20today</small></div><div%20class="grid-col-3%20grid-col--align-center"%20style="%20float:%20none;display:%20inline-block;"><h3%20class="padding-right--quarter">'+CCDATA.user.streak_hash.max_count+'</h3><small>day%20best%20streak</small></div></div></div></article>')})}})();

