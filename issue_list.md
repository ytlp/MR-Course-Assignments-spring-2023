## 说明
本次实验的主要内容是给每个任务中对应位置的文件添加Apache License许可证。在使用Apache License的开源项目的每个源码文件均需要添加上Apache License的通告声明：
```
Copyright 2022 The Fluid Author.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

每个任务需要完成的内容是将上述内容以**块注释**的形式添加到对应位置文件的开头部分。
### 情况一
例如`pkg/utils/dataset/lifecycle/node_test.go`文件目前不存在Apache License的通告声明，该文件的开头内容原本为
```go
   
package lifecycle

import (
	"fmt"
	"reflect"
	"testing"

	datav1alpha1 "github.com/fluid-cloudnative/fluid/api/v1alpha1"
	"github.com/fluid-cloudnative/fluid/pkg/common"
	"github.com/fluid-cloudnative/fluid/pkg/ddc/base"
	"github.com/fluid-cloudnative/fluid/pkg/utils/kubeclient"
	v1 "k8s.io/api/core/v1"
	"k8s.io/apimachinery/pkg/api/resource"
	metav1 "k8s.io/apimachinery/pkg/apis/meta/v1"
	"k8s.io/apimachinery/pkg/runtime"
	"sigs.k8s.io/controller-runtime/pkg/client/fake"
)
```
你需要将通告声明以**注释**的形式添加到该文件的开头。内容如下：
```go
/*
Copyright 2022 The Fluid Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
*/

package lifecycle

import (
	"fmt"
	"reflect"
	"testing"

	datav1alpha1 "github.com/fluid-cloudnative/fluid/api/v1alpha1"
	"github.com/fluid-cloudnative/fluid/pkg/common"
	"github.com/fluid-cloudnative/fluid/pkg/ddc/base"
	"github.com/fluid-cloudnative/fluid/pkg/utils/kubeclient"
	v1 "k8s.io/api/core/v1"
	"k8s.io/apimachinery/pkg/api/resource"
	metav1 "k8s.io/apimachinery/pkg/apis/meta/v1"
	"k8s.io/apimachinery/pkg/runtime"
	"sigs.k8s.io/controller-runtime/pkg/client/fake"
)
```

> 注意：License块注释与`package xxx`间需要包含一个空行

### 情况二
第二种情况是，文件包含Apache License的通告声明，但缺少Copyright，因此该通告声明仍然是不规范的。

例如，`pkg/controllers/v1alpha1/goosefs/suite_test.go`开头为：
```go
/*

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
*/

package goosefs
```

需要规范化该通告声明，增加Copyright，改为以下内容：
```go
/*
Copyright 2022 The Fluid Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
*/

package goosefs
```

> 注意：License块注释与`package xxx`间需要包含一个空行

### 情况三
第三种情况是文件包含Apache License的通告声明和Copyright，但年份信息不正确。

例如，`pkg/controllers/v1alpha1/dataload/implement_test.go`开头为：
```go
/*
Copyright 2021 The Fluid Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
*/

package dataload
```

需要规范化该通告声明，将Copyright 2021 改为Copyright 2022，改为以下内容：
```go
/*
Copyright 2022 The Fluid Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
*/

package dataload
```

> 注意：License块注释与`package xxx`间需要包含一个空行



**修改完成后提交Pull Request并被合并，即完成了该Task。**

## Task列表

### Task 1

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/webhook/plugins/mountpropagationinjector/mount_propagation_injector.go`

### Task 2

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/webhook/plugins/mountpropagationinjector/mount_propagation_injector_test.go`

### Task 3

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/webhook/scheduler/mutating/utils.go`

### Task 4

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/dump/dump.go`

### Task 5

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/csi/updatedbconf/register.go`

### Task 6

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/csi/updatedbconf/updatedbconf.go`

### Task 7

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/csi/updatedbconf/updatedbconf_test.go`

### Task 8

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/csi/plugins/controller.go`

### Task 9

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/csi/plugins/driver.go`

### Task 10

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/csi/plugins/nodeserver.go`

### Task 11

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/factory.go`

### Task 12

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/eac/transform_test.go`

### Task 13

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/eac/transform_port_test.go`

### Task 14

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/eac/ufs_test.go`

### Task 15

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/eac/transform_option_test.go`

### Task 16

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/eac/transform_image_test.go`

### Task 17

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/types_selector.go`

### Task 18

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/replicas.go`

### Task 19

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_resources.go`

### Task 20

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_test.go`

### Task 21

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/metadata.go`

### Task 22

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/utils_test.go`

### Task 23

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/deprecated_label.go`

### Task 24

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/api_gateway.go`

### Task 25

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_permission_test.go`

### Task 26

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_ufs_test.go`

### Task 27

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/types.go`

### Task 28

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/ufs.go`

### Task 29

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/engine_test.go`

### Task 30

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/shutdown.go`

### Task 31

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/cache.go`

### Task 32

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_init_users.go`

### Task 33

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_fuse_test.go`

### Task 34

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/shutdown_engine_test.go`

### Task 35

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_optimization_test.go`

### Task 36

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/runtime_info.go`

### Task 37

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/create_volume.go`

### Task 38

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_permission.go`

### Task 39

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/hcfs.go`

### Task 40

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/health_check_test.go`

### Task 41

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/health_check.go`

### Task 42

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/ufs_test.go`

### Task 43

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform.go`

### Task 44

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/label.go`

### Task 45

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_init_users_test.go`

### Task 46

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/delete_volume.go`

### Task 47

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_fuse.go`

### Task 48

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/master.go`

### Task 49

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/utils.go`

### Task 50

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/engine.go`

### Task 51

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/ufs_internal.go`

### Task 52

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_optimization.go`

### Task 53

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/dataset.go`

### Task 54

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_resources_test.go`

### Task 55

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/const.go`

### Task 56

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_hadoop_config.go`

### Task 57

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/report.go`

### Task 58

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/master_internal.go`

### Task 59

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_ufs.go`

### Task 60

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/transform_volumes_test.go`

### Task 61

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/runtime_info_test.go`

### Task 62

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/operations/local_test.go`

### Task 63

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/operations/base_test.go`

### Task 64

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/operations/cached.go`

### Task 65

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/operations/conf.go`

### Task 66

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/operations/local.go`

### Task 67

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/alluxio/operations/base.go`

### Task 68

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/port_parser_test.go`

### Task 69

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/deprecated_label.go`

### Task 70

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/cache_test.go`

### Task 71

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/worker.go`

### Task 72

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/master.go`

### Task 73

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/load_data_test.go`

### Task 74

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/jindo/operations/cached.go`

### Task 75

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/goosefs/port_parser_test.go`

### Task 76

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/goosefs/utils_test.go`

### Task 77

任务内容：文件头部添加或规范化License内容

修改位置：`pkg/ddc/goosefs/worker.go`