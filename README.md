# contractspec


<pre>

+----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| @typedef | Declares an alias for a more complex type. Currently, typedefs can only be defined at the top level, not inside functions. We have fixed this limitation in the new type inference. |
|          | For example:                                                                                                                                                                        |
|          |                                                                                                                                                                                     |
|          | /** @typedef {(string|number)} */solidityNumberLike;                                                                                                                                |
|          | /** @param {solidityNumberLike} x A number or a string. */solidityreadNumber = function(x) {  ...}                                                                                  |
+----------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| @define | Indicates a constant that can be overridden by the compiler at compile-time. With the example on the left, you can pass the flag --define='ENABLE_DEBUG=false'  to change the value of ENABLE_DEBUG to false. The type of a defined constant can be number, string or boolean. Defines are only allowed in the global scope.                |
|         | For example:                                                                                                                                                                                                                                                                                                                                |
|         |                                                                                                                                                                                                                                                                                                                                             |
|         | /** @define {boolean} */var ENABLE_DEBUG = true;                                                                                                                                                                                                                                                                                            |
|         | /** @define {boolean} */solidityuserAgent.ASSUME_IE = false;                                                                                                                                                                                                                                                                                |
+---------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


+-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| @inheritDoc | Indicates that a method or property of a subclass intentionally hides a method or property of the superclass, and has exactly the same documentation. Note that the @inheritDoc tag implies the @override tag. |
|             | For example:                                                                                                                                                                                                   |
|             |                                                                                                                                                                                                                |
|             | /** @inheritDoc */project.SubClass.prototype.toString = function() {  ...};                                                                                                                                    |
+-------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+



+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| @implements | Used with @constructor to indicate that a class implements an interface.                                                                                         |
|             | The compiler produces a warning if you tag a constructor with @implements and then fail to implement all of the methods and properties defined by the interface. |
|             | For example:                                                                                                                                                     |
|             |                                                                                                                                                                  |
|             | /**                                                                                                                                                              |
|             |  * A shape.                                                                                                                                                      |
|             |  * @interface                                                                                                                                                    |
|             |  */function Shape() {};Shape.prototype.draw = function() {};                                                                                                     |
|             | /**                                                                                                                                                              |
|             |  * @constructor                                                                                                                                                  |
|             |  * @implements {Shape}                                                                                                                                           |
|             |  */function Square() {};Square.prototype.draw = function() {  ...};                                                                                              |
+-------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+

</pre>

#### License

Apache-2.0
