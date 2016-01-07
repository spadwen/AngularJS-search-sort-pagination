# AngularJS-search-sort-pagination
AngularJS: Display data using ng-repeat; Implement search (filter); Implement sort (orderBy); Implement pagination (dirPaginate).

Live site at http://dwinfoserver.com/shares

link <script src="http://dwinfoserver.com/shares/dirPagination.js"></script>

Codes:
 <tr dir-paginate="x in names|orderBy:sortKey:reverse|filter:search|itemsPerPage:15">
 
 notes: 1) search feature => filter:search
            <div class="form-group">
           
            <input type="text" ng-model="search" class="form-control" placeholder="Search">
           </div>
           
        2) sort feature => orderBy:sortKey:reverse
            
           AngularJS script:
           $scope.sort = function(keyname){
             $scope.sortKey = keyname;   //set the sortKey to the param passed
             $scope.reverse = !$scope.reverse; //if true make it false and vice versa
             }
             
           Sample table field head:
             <th ng-click="sort('ASXCode')">ASX<br> Code
              <span class="glyphicon sort-icon" ng-show="sortKey=='ASXCode'" ng-class="{'glyphicon-chevron-up':reverse,'glyphicon-chevron-down':!reverse}"></span>
             </th>
        3) pagination feature => itemsPerPage:15
             <dir-pagination-controls
					    max-size="15" (maximum number of page numbers to show)
					    direction-links="true" (Next page and previous page links true/false)
				   	  boundary-links="true" > (First page and last page links true/false)
				    </dir-pagination-controls>
