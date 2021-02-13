# AWSQS::EKS::Cluster ResourcesVpcConfig

An object that represents the virtual private cloud (VPC) configuration to use for an Amazon EKS cluster.

## Syntax

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON

<pre>
{
    "<a href="#securitygroupids" title="SecurityGroupIds">SecurityGroupIds</a>" : <i>[ String, ... ]</i>,
    "<a href="#subnetids" title="SubnetIds">SubnetIds</a>" : <i>[ String, ... ]</i>,
    "<a href="#endpointpublicaccess" title="EndpointPublicAccess">EndpointPublicAccess</a>" : <i>Boolean</i>,
    "<a href="#endpointprivateaccess" title="EndpointPrivateAccess">EndpointPrivateAccess</a>" : <i>Boolean</i>,
    "<a href="#publicaccesscidrs" title="PublicAccessCidrs">PublicAccessCidrs</a>" : <i>[ String, ... ]</i>
}
</pre>

### YAML

<pre>
<a href="#securitygroupids" title="SecurityGroupIds">SecurityGroupIds</a>: <i>
      - String</i>
<a href="#subnetids" title="SubnetIds">SubnetIds</a>: <i>
      - String</i>
<a href="#endpointpublicaccess" title="EndpointPublicAccess">EndpointPublicAccess</a>: <i>Boolean</i>
<a href="#endpointprivateaccess" title="EndpointPrivateAccess">EndpointPrivateAccess</a>: <i>Boolean</i>
<a href="#publicaccesscidrs" title="PublicAccessCidrs">PublicAccessCidrs</a>: <i>
      - String</i>
</pre>

## Properties

#### SecurityGroupIds

Specify one or more security groups for the cross-account elastic network interfaces that Amazon EKS creates to allow communication between worker nodes and the Kubernetes control plane. If you don't specify a security group, the default VPC security group is used.

_Required_: No

_Type_: List of String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### SubnetIds

Specify subnets for your Amazon EKS worker nodes. Amazon EKS creates cross-account elastic network interfaces in these subnets to allow communication between worker nodes and the Kubernetes control plane.

_Required_: Yes

_Type_: List of String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### EndpointPublicAccess

Set this value to "false" to disable public access to the cluster's Kubernetes API server endpoint. If you disable public access, your cluster's Kubernetes API server receives requests only from within the VPC cluster. The default value for this parameter is "true," which enables public access to the Kubernetes API server.

_Required_: No

_Type_: Boolean

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### EndpointPrivateAccess

Set this value to "true" to enable private access for your cluster's Kubernetes API server endpoint. If you enable private access, Kubernetes API requests from within the cluster's VPC uses the private VPC endpoint. The default value for this parameter is "false," which disables private access for your Kubernetes API server. If you disable private access and have worker nodes or AWS Fargate pods in the cluster, ensure that `publicAccessCidrs` includes the necessary CIDR blocks for communication with the worker nodes or Fargate pods.

_Required_: No

_Type_: Boolean

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### PublicAccessCidrs

CIDR blocks that are allowed to access the cluster's public Kubernetes API server endpoint. Communication to the endpoint from addresses outside of the specified CIDR blocks is denied. The default value is `0.0.0.0/0`. If you disable private endpoint access and you have worker nodes or AWS Fargate pods in the cluster, ensure that you specify the necessary CIDR blocks.

_Required_: No

_Type_: List of String

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

