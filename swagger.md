# 生成swagger.json
swagger generate spec -o ./swagger.json

# @Param
@Param指的是用户请求的参数，可以是url路径（path）、query、body。如果不需要参数（例如get all类型的，由url就齐活了），则不需要加@Param。参数可以是 int 或者 string 类型。这里的定义会影响swagger ui发送的请求，如果定义错了会导致发送请求的数据不对，例如对数字进行了转义。

Param group body model.SwagGroupAdd true "Add group"