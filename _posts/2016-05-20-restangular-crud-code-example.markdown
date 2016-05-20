---
title:  "Restangular Crud code example"
date:   2016-05-20 02:39:00
summary: From the documentation.
---

{% highlight JavaScript %}
// Here we use then to resolve the promise.
Restangular.all('users').getList().then(function(users) {
    $scope.users   = users;
    var userWithId = _.find(users, function(user) {
        return user.id === 123456;
    });

    userWithId.name = "Gonto";
    userWithId.put();

    // Alternatively delete the element from the list when finished
    userWithId.remove().then(function() {
        // Updating the list and removing the user after the response is OK.
        $scope.users = _.without($scope.users, userWithId);
    });

});
{% endhighlight %}