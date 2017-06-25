<!DOCTYPE html>
<html>
<head>
<title>玩转spring boot——websocket</title>
<script src="//cdn.bootcss.com/angular.js/1.5.6/angular.min.js"></script>
<script src="https://cdn.bootcss.com/sockjs-client/1.1.4/sockjs.min.js"></script>
<script src="https://cdn.bootcss.com/stomp.js/2.3.3/stomp.min.js"></script>
<script type="text/javascript">
	/*<![CDATA[*/

	var stompClient = null;

	var app = angular.module('app', []);
	app.controller('MainController', function($rootScope, $scope, $http) {

		$scope.data = {
			//连接状态
			connected : false,
			//消息
			message : '',
			rows : []
		};

		//连接
		$scope.connect = function() {
			var socket = new SockJS('/my-websocket');
			stompClient = Stomp.over(socket);
			stompClient.connect({}, function(frame) {
				// 注册发送消息
				stompClient.subscribe('/topic/send', function(msg) {
					$scope.data.rows.push(JSON.parse(msg.body));
					$scope.data.connected = true;
					$scope.$apply();
				});
				// 注册推送时间回调
				stompClient.subscribe('/topic/callback', function(r) {
					$scope.data.time = '当前服务器时间：' + r.body;
					$scope.data.connected = true;
					$scope.$apply();
				});

				$scope.data.connected = true;
				$scope.$apply();
			});
		};

		$scope.disconnect = function() {
			if (stompClient != null) {
				stompClient.disconnect();
			}
			$scope.data.connected = false;
		}

		$scope.send = function() {
			stompClient.send("/app/send", {}, JSON.stringify({
				'message' : $scope.data.message
			}));
		}
	});
	/*]]>*/
</script>
</head>
<body ng-app="app" ng-controller="MainController">

	<h2>玩转spring boot——websocket</h2>
	<h4>
		出处：刘冬博客 <a href="http://www.cnblogs.com/goodhelper">http://www.cnblogs.com/goodhelper</a>
	</h4>

	<label>WebSocket连接状态:</label>
	<button type="button" ng-disabled="data.connected" ng-click="connect()">连接</button>
	<button type="button" ng-click="disconnect()"
		ng-disabled="!data.connected">断开</button>
	<br />
	<br />
	<div ng-show="data.connected">
		<label>{{data.time}}</label> <br /> <br /> <input type="text"
			ng-model="data.message" placeholder="请输入内容..." />
		<button ng-click="send()" type="button">发送</button>
		<br /> <br /> 消息列表： <br />
		<table>
			<thead>
				<tr>
					<th>内容</th>
					<th>时间</th>
				</tr>
			</thead>
			<tbody>
				<tr ng-repeat="row in data.rows">
					<td>{{row.message}}</td>
					<td>{{row.date}}</td>
				</tr>
			</tbody>
		</table>
	</div>
</body>
</html>