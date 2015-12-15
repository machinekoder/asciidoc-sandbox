# Protocol Documentation
<a name="top"/>

## Table of Contents
* [canon.proto](#canon.proto)
 * [Emc_Aux_Input_Wait](#pb.Emc_Aux_Input_Wait)
 * [Emc_Exec_Plugin_Ca1l](#pb.Emc_Exec_Plugin_Ca1l)
 * [Emc_Io_Plugin_Call](#pb.Emc_Io_Plugin_Call)
 * [Emc_Motion_Adaptive](#pb.Emc_Motion_Adaptive)
 * [Emc_Motion_Set_Aout](#pb.Emc_Motion_Set_Aout)
 * [Emc_Motion_Set_Dout](#pb.Emc_Motion_Set_Dout)
 * [Emc_Operator_Display](#pb.Emc_Operator_Display)
 * [Emc_Operator_Error](#pb.Emc_Operator_Error)
 * [Emc_Operator_Text](#pb.Emc_Operator_Text)
 * [Emc_Spindle_On](#pb.Emc_Spindle_On)
 * [Emc_Spindle_Orient](#pb.Emc_Spindle_Orient)
 * [Emc_Spindle_Speed](#pb.Emc_Spindle_Speed)
 * [Emc_Spindle_Wait_Orient_Complete](#pb.Emc_Spindle_Wait_Orient_Complete)
 * [Emc_Tool_Prepare](#pb.Emc_Tool_Prepare)
 * [Emc_Tool_Set_Number](#pb.Emc_Tool_Set_Number)
 * [Emc_Tool_Set_Offset](#pb.Emc_Tool_Set_Offset)
 * [Emc_Traj_Circular_Move](#pb.Emc_Traj_Circular_Move)
 * [Emc_Traj_Delay](#pb.Emc_Traj_Delay)
 * [Emc_Traj_Linear_Move](#pb.Emc_Traj_Linear_Move)
 * [Emc_Traj_Probe](#pb.Emc_Traj_Probe)
 * [Emc_Traj_Rigid_Tap](#pb.Emc_Traj_Rigid_Tap)
 * [Emc_Traj_Set_Fh_Enable](#pb.Emc_Traj_Set_Fh_Enable)
 * [Emc_Traj_Set_Fo_Enable](#pb.Emc_Traj_Set_Fo_Enable)
 * [Emc_Traj_Set_G5x](#pb.Emc_Traj_Set_G5x)
 * [Emc_Traj_Set_G92](#pb.Emc_Traj_Set_G92)
 * [Emc_Traj_Set_Offset](#pb.Emc_Traj_Set_Offset)
 * [Emc_Traj_Set_Rotation](#pb.Emc_Traj_Set_Rotation)
 * [Emc_Traj_Set_So_Enable](#pb.Emc_Traj_Set_So_Enable)
 * [Emc_Traj_Set_Spindlesync](#pb.Emc_Traj_Set_Spindlesync)
 * [Emc_Traj_Set_Term_Cond](#pb.Emc_Traj_Set_Term_Cond)
* [config.proto](#config.proto)
 * [Application](#pb.Application)
 * [File](#pb.File)
 * [Launcher](#pb.Launcher)
 * [MachineInfo](#pb.MachineInfo)
 * [StdoutLine](#pb.StdoutLine)
 * [ApplicationType](#pb.ApplicationType)
 * [FileContent](#pb.FileContent)
* [emcclass.proto](#emcclass.proto)
 * [EmcPose](#pb.EmcPose)
 * [PmCartesian](#pb.PmCartesian)
* [log.proto](#log.proto)
 * [LogMessage](#pb.LogMessage)
* [message.proto](#message.proto)
 * [Container](#pb.Container)
* [motcmds.proto](#motcmds.proto)
 * [MotionCommand](#pb.MotionCommand)
 * [MotionStatus](#pb.MotionStatus)
 * [MotionType](#pb.MotionType)
 * [cmd_code_t](#pb.cmd_code_t)
 * [cmd_status_t](#pb.cmd_status_t)
* [nanopb.proto](#nanopb.proto)
 * [NanoPBOptions](#NanoPBOptions)
 * [FieldType](#FieldType)
 * [IntSize](#IntSize)
* [object.proto](#object.proto)
 * [AnError](#pb.AnError)
 * [Component](#pb.Component)
 * [Function](#pb.Function)
 * [Group](#pb.Group)
 * [Inst](#pb.Inst)
 * [Instance](#pb.Instance)
 * [Member](#pb.Member)
 * [Originator](#pb.Originator)
 * [Param](#pb.Param)
 * [Pin](#pb.Pin)
 * [ProtocolParameters](#pb.ProtocolParameters)
 * [Ring](#pb.Ring)
 * [ServiceAnnouncement](#pb.ServiceAnnouncement)
 * [Signal](#pb.Signal)
 * [Thread](#pb.Thread)
 * [Vtable](#pb.Vtable)
* [param.proto](#param.proto)
 * [ParamKey](#pb.ParamKey)
 * [ParamType](#pb.ParamType)
* [preview.proto](#preview.proto)
 * [Position](#pb.Position)
 * [Preview](#pb.Preview)
 * [KinematicsType](#pb.KinematicsType)
 * [PreviewOpType](#pb.PreviewOpType)
 * [SourceType](#pb.SourceType)
* [rtapi_message.proto](#rtapi_message.proto)
 * [RTAPI_Message](#pb.RTAPI_Message)
* [rtapicommand.proto](#rtapicommand.proto)
 * [RTAPICommand](#pb.RTAPICommand)
* [status.proto](#status.proto)
 * [EmcCommandParameters](#pb.EmcCommandParameters)
 * [EmcProgramExtension](#pb.EmcProgramExtension)
 * [EmcStatusAnalogIO](#pb.EmcStatusAnalogIO)
 * [EmcStatusConfig](#pb.EmcStatusConfig)
 * [EmcStatusConfigAxis](#pb.EmcStatusConfigAxis)
 * [EmcStatusDigitalIO](#pb.EmcStatusDigitalIO)
 * [EmcStatusGCode](#pb.EmcStatusGCode)
 * [EmcStatusInterp](#pb.EmcStatusInterp)
 * [EmcStatusIo](#pb.EmcStatusIo)
 * [EmcStatusLimit](#pb.EmcStatusLimit)
 * [EmcStatusMCode](#pb.EmcStatusMCode)
 * [EmcStatusMotion](#pb.EmcStatusMotion)
 * [EmcStatusMotionAxis](#pb.EmcStatusMotionAxis)
 * [EmcStatusSetting](#pb.EmcStatusSetting)
 * [EmcStatusTask](#pb.EmcStatusTask)
 * [EmcStatusUserCommand](#pb.EmcStatusUserCommand)
 * [EmcToolData](#pb.EmcToolData)
 * [EmcAngularUnitsType](#pb.EmcAngularUnitsType)
 * [EmcAxisType](#pb.EmcAxisType)
 * [EmcCanonUnitsType](#pb.EmcCanonUnitsType)
 * [EmcInterpExitCodeType](#pb.EmcInterpExitCodeType)
 * [EmcInterpStateType](#pb.EmcInterpStateType)
 * [EmcKinematicsType](#pb.EmcKinematicsType)
 * [EmcLinearUnitsType](#pb.EmcLinearUnitsType)
 * [EmcPositionFeedbackType](#pb.EmcPositionFeedbackType)
 * [EmcPositionOffsetType](#pb.EmcPositionOffsetType)
 * [EmcTaskExecStateType](#pb.EmcTaskExecStateType)
 * [EmcTaskModeType](#pb.EmcTaskModeType)
 * [EmcTaskStateType](#pb.EmcTaskStateType)
 * [EmcTimeUnitsType](#pb.EmcTimeUnitsType)
 * [EmcTrajectoryModeType](#pb.EmcTrajectoryModeType)
* [task.proto](#task.proto)
 * [TaskPlanBlockDelete](#pb.TaskPlanBlockDelete)
 * [TaskPlanExecute](#pb.TaskPlanExecute)
 * [TaskPlanOpen](#pb.TaskPlanOpen)
 * [TaskPlanOptionalStop](#pb.TaskPlanOptionalStop)
 * [TaskPlanReply](#pb.TaskPlanReply)
 * [TaskReply](#pb.TaskReply)
 * [TicketUpdate](#pb.TicketUpdate)
* [test.proto](#test.proto)
 * [Test1](#pb.Test1)
 * [Test2](#pb.Test2)
 * [Test3](#pb.Test3)
 * [TestOpType](#pb.TestOpType)
* [types.proto](#types.proto)
 * [CanonDirection](#pb.CanonDirection)
 * [ContainerType](#pb.ContainerType)
 * [HalParamDirection](#pb.HalParamDirection)
 * [HalPinDirection](#pb.HalPinDirection)
 * [InputType](#pb.InputType)
 * [InterpreterStateType](#pb.InterpreterStateType)
 * [MsgLevel](#pb.MsgLevel)
 * [MsgOrigin](#pb.MsgOrigin)
 * [ObjectType](#pb.ObjectType)
 * [OriginDetail](#pb.OriginDetail)
 * [OriginIndex](#pb.OriginIndex)
 * [OriginType](#pb.OriginType)
 * [RCS_STATUS](#pb.RCS_STATUS)
 * [ReplyType](#pb.ReplyType)
 * [ServiceAPI](#pb.ServiceAPI)
 * [ServiceType](#pb.ServiceType)
 * [Severity](#pb.Severity)
 * [StatusType](#pb.StatusType)
 * [TermConditionType](#pb.TermConditionType)
 * [ValueType](#pb.ValueType)
 * [WaitType](#pb.WaitType)
* [value.proto](#value.proto)
 * [Value](#pb.Value)
* [Scalar Value Types](#scalar-value-types)

<a name="canon.proto"/>
<p align="right"><a href="#top">Top</a></p>

## canon.proto

<a name="pb.Emc_Aux_Input_Wait"/>
### Emc_Aux_Input_Wait


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Aux_Input_Wait.index"/> index | [uint32](#uint32) | required |  |
| <a name="pb.Emc_Aux_Input_Wait.input_type"/> input_type | [InputType](#pb.InputType) | required |  |
| <a name="pb.Emc_Aux_Input_Wait.wait_type"/> wait_type | [WaitType](#pb.WaitType) | required |  |
| <a name="pb.Emc_Aux_Input_Wait.timeout"/> timeout | [double](#double) | required |  |

<a name="pb.Emc_Exec_Plugin_Ca1l"/>
### Emc_Exec_Plugin_Ca1l


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Exec_Plugin_Ca1l.call"/> call | [bytes](#bytes) | required |  |

<a name="pb.Emc_Io_Plugin_Call"/>
### Emc_Io_Plugin_Call


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Io_Plugin_Call.call"/> call | [bytes](#bytes) | required |  |

<a name="pb.Emc_Motion_Adaptive"/>
### Emc_Motion_Adaptive


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Motion_Adaptive.status"/> status | [bool](#bool) | required |  |

<a name="pb.Emc_Motion_Set_Aout"/>
### Emc_Motion_Set_Aout


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Motion_Set_Aout.index"/> index | [uint32](#uint32) | required |  |
| <a name="pb.Emc_Motion_Set_Aout.start"/> start | [double](#double) | required |  |
| <a name="pb.Emc_Motion_Set_Aout.end"/> end | [double](#double) | required |  |
| <a name="pb.Emc_Motion_Set_Aout.now"/> now | [bool](#bool) | required |  |

<a name="pb.Emc_Motion_Set_Dout"/>
### Emc_Motion_Set_Dout


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Motion_Set_Dout.index"/> index | [uint32](#uint32) | required |  |
| <a name="pb.Emc_Motion_Set_Dout.start"/> start | [bool](#bool) | required |  |
| <a name="pb.Emc_Motion_Set_Dout.end"/> end | [bool](#bool) | required |  |
| <a name="pb.Emc_Motion_Set_Dout.now"/> now | [bool](#bool) | required |  |

<a name="pb.Emc_Operator_Display"/>
### Emc_Operator_Display


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Operator_Display.id"/> id | [int32](#int32) | required |  |
| <a name="pb.Emc_Operator_Display.display"/> display | [string](#string) | required |  |

<a name="pb.Emc_Operator_Error"/>
### Emc_Operator_Error


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Operator_Error.id"/> id | [int32](#int32) | required |  |
| <a name="pb.Emc_Operator_Error.error"/> error | [string](#string) | required |  |

<a name="pb.Emc_Operator_Text"/>
### Emc_Operator_Text


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Operator_Text.id"/> id | [int32](#int32) | required |  |
| <a name="pb.Emc_Operator_Text.text"/> text | [string](#string) | required |  |

<a name="pb.Emc_Spindle_On"/>
### Emc_Spindle_On


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Spindle_On.speed"/> speed | [double](#double) | required |  |
| <a name="pb.Emc_Spindle_On.factor"/> factor | [double](#double) | required |  |
| <a name="pb.Emc_Spindle_On.xoffset"/> xoffset | [double](#double) | required |  |

<a name="pb.Emc_Spindle_Orient"/>
### Emc_Spindle_Orient


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Spindle_Orient.orientation"/> orientation | [double](#double) | required |  |
| <a name="pb.Emc_Spindle_Orient.mode"/> mode | [CanonDirection](#pb.CanonDirection) | required |  |

<a name="pb.Emc_Spindle_Speed"/>
### Emc_Spindle_Speed


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Spindle_Speed.speed"/> speed | [double](#double) | required |  |
| <a name="pb.Emc_Spindle_Speed.factor"/> factor | [double](#double) | required |  |
| <a name="pb.Emc_Spindle_Speed.xoffset"/> xoffset | [double](#double) | required |  |

<a name="pb.Emc_Spindle_Wait_Orient_Complete"/>
### Emc_Spindle_Wait_Orient_Complete


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Spindle_Wait_Orient_Complete.timeout"/> timeout | [double](#double) | required |  |

<a name="pb.Emc_Tool_Prepare"/>
### Emc_Tool_Prepare


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Tool_Prepare.pocket"/> pocket | [int32](#int32) | required |  |
| <a name="pb.Emc_Tool_Prepare.tool"/> tool | [int32](#int32) | required |  |

<a name="pb.Emc_Tool_Set_Number"/>
### Emc_Tool_Set_Number


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Tool_Set_Number.tool"/> tool | [int32](#int32) | required |  |

<a name="pb.Emc_Tool_Set_Offset"/>
### Emc_Tool_Set_Offset


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Tool_Set_Offset.pocket"/> pocket | [int32](#int32) | required |  |
| <a name="pb.Emc_Tool_Set_Offset.toolno"/> toolno | [int32](#int32) | required |  |
| <a name="pb.Emc_Tool_Set_Offset.offset"/> offset | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Emc_Tool_Set_Offset.diameter"/> diameter | [double](#double) | required |  |
| <a name="pb.Emc_Tool_Set_Offset.frontangle"/> frontangle | [double](#double) | required |  |
| <a name="pb.Emc_Tool_Set_Offset.backangle"/> backangle | [double](#double) | required |  |
| <a name="pb.Emc_Tool_Set_Offset.orientation"/> orientation | [int32](#int32) | required |  |

<a name="pb.Emc_Traj_Circular_Move"/>
### Emc_Traj_Circular_Move


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Circular_Move.type"/> type | [MotionType](#pb.MotionType) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.end"/> end | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.center"/> center | [PmCartesian](#pb.PmCartesian) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.normal"/> normal | [PmCartesian](#pb.PmCartesian) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.vel"/> vel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.ini_maxvel"/> ini_maxvel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.acc"/> acc | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.feed_mode"/> feed_mode | [bool](#bool) | required |  |
| <a name="pb.Emc_Traj_Circular_Move.turn"/> turn | [int32](#int32) | required |  |

<a name="pb.Emc_Traj_Delay"/>
### Emc_Traj_Delay


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Delay.delay"/> delay | [double](#double) | required |  |

<a name="pb.Emc_Traj_Linear_Move"/>
### Emc_Traj_Linear_Move


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Linear_Move.type"/> type | [MotionType](#pb.MotionType) | required |  |
| <a name="pb.Emc_Traj_Linear_Move.end"/> end | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Emc_Traj_Linear_Move.vel"/> vel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Linear_Move.ini_maxvel"/> ini_maxvel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Linear_Move.acc"/> acc | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Linear_Move.feed_mode"/> feed_mode | [bool](#bool) | required |  |
| <a name="pb.Emc_Traj_Linear_Move.indexrotary"/> indexrotary | [int32](#int32) | required |  |

<a name="pb.Emc_Traj_Probe"/>
### Emc_Traj_Probe


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Probe.type"/> type | [MotionType](#pb.MotionType) | required |  |
| <a name="pb.Emc_Traj_Probe.pos"/> pos | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Emc_Traj_Probe.vel"/> vel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Probe.ini_maxvel"/> ini_maxvel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Probe.acc"/> acc | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Probe.probe_type"/> probe_type | [uint32](#uint32) | required |  |

<a name="pb.Emc_Traj_Rigid_Tap"/>
### Emc_Traj_Rigid_Tap


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Rigid_Tap.pos"/> pos | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Emc_Traj_Rigid_Tap.vel"/> vel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Rigid_Tap.ini_maxvel"/> ini_maxvel | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Rigid_Tap.acc"/> acc | [double](#double) | required |  |

<a name="pb.Emc_Traj_Set_Fh_Enable"/>
### Emc_Traj_Set_Fh_Enable


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_Fh_Enable.mode"/> mode | [bool](#bool) | required |  |

<a name="pb.Emc_Traj_Set_Fo_Enable"/>
### Emc_Traj_Set_Fo_Enable


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_Fo_Enable.mode"/> mode | [bool](#bool) | required |  |

<a name="pb.Emc_Traj_Set_G5x"/>
### Emc_Traj_Set_G5x


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_G5x.origin"/> origin | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Emc_Traj_Set_G5x.g5x_index"/> g5x_index | [OriginIndex](#pb.OriginIndex) | required |  |

<a name="pb.Emc_Traj_Set_G92"/>
### Emc_Traj_Set_G92


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_G92.origin"/> origin | [EmcPose](#pb.EmcPose) | required |  |

<a name="pb.Emc_Traj_Set_Offset"/>
### Emc_Traj_Set_Offset


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_Offset.offset"/> offset | [EmcPose](#pb.EmcPose) | required |  |

<a name="pb.Emc_Traj_Set_Rotation"/>
### Emc_Traj_Set_Rotation


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_Rotation.rotation"/> rotation | [double](#double) | required |  |

<a name="pb.Emc_Traj_Set_So_Enable"/>
### Emc_Traj_Set_So_Enable


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_So_Enable.mode"/> mode | [bool](#bool) | required |  |

<a name="pb.Emc_Traj_Set_Spindlesync"/>
### Emc_Traj_Set_Spindlesync


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_Spindlesync.feed_per_revolution"/> feed_per_revolution | [double](#double) | required |  |
| <a name="pb.Emc_Traj_Set_Spindlesync.velocity_mode"/> velocity_mode | [bool](#bool) | required |  |

<a name="pb.Emc_Traj_Set_Term_Cond"/>
### Emc_Traj_Set_Term_Cond


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Emc_Traj_Set_Term_Cond.cond"/> cond | [TermConditionType](#pb.TermConditionType) | required |  |
| <a name="pb.Emc_Traj_Set_Term_Cond.tolerance"/> tolerance | [double](#double) | required |  |


<a name="config.proto"/>
<p align="right"><a href="#top">Top</a></p>

## config.proto

<a name="pb.Application"/>
### Application


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Application.name"/> name | [string](#string) | required |  |
| <a name="pb.Application.description"/> description | [string](#string) | optional |  |
| <a name="pb.Application.type"/> type | [ApplicationType](#pb.ApplicationType) | optional |  |
| <a name="pb.Application.weburi"/> weburi | [string](#string) | optional |  |
| <a name="pb.Application.file"/> file | [File](#pb.File) | repeated |  |

<a name="pb.File"/>
### File


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.File.name"/> name | [string](#string) | required |  |
| <a name="pb.File.encoding"/> encoding | [FileContent](#pb.FileContent) | required |  |
| <a name="pb.File.blob"/> blob | [bytes](#bytes) | optional |  |

<a name="pb.Launcher"/>
### Launcher


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Launcher.index"/> index | [int32](#int32) | required |  |
| <a name="pb.Launcher.name"/> name | [string](#string) | optional |  |
| <a name="pb.Launcher.description"/> description | [string](#string) | optional |  |
| <a name="pb.Launcher.image"/> image | [File](#pb.File) | optional |  |
| <a name="pb.Launcher.info"/> info | [MachineInfo](#pb.MachineInfo) | optional |  |
| <a name="pb.Launcher.running"/> running | [bool](#bool) | optional |  |
| <a name="pb.Launcher.terminating"/> terminating | [bool](#bool) | optional |  |
| <a name="pb.Launcher.command"/> command | [string](#string) | optional |  |
| <a name="pb.Launcher.shell"/> shell | [bool](#bool) | optional |  |
| <a name="pb.Launcher.output"/> output | [StdoutLine](#pb.StdoutLine) | repeated |  |
| <a name="pb.Launcher.returncode"/> returncode | [int32](#int32) | optional |  |
| <a name="pb.Launcher.workdir"/> workdir | [string](#string) | optional |  |

<a name="pb.MachineInfo"/>
### MachineInfo


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.MachineInfo.type"/> type | [string](#string) | optional |  |
| <a name="pb.MachineInfo.manufacturer"/> manufacturer | [string](#string) | optional |  |
| <a name="pb.MachineInfo.model"/> model | [string](#string) | optional |  |
| <a name="pb.MachineInfo.variant"/> variant | [string](#string) | optional |  |

<a name="pb.StdoutLine"/>
### StdoutLine


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.StdoutLine.index"/> index | [int32](#int32) | required |  |
| <a name="pb.StdoutLine.line"/> line | [string](#string) | optional |  |


<a name="pb.ApplicationType"/>
### ApplicationType


| Name | Number | Description |
| ---- | ------ | ----------- |
| QT5_QML | 1 |  |
| GLADEVCP | 2 |  |
| JAVASCRIPT | 3 |  |

<a name="pb.FileContent"/>
### FileContent


| Name | Number | Description |
| ---- | ------ | ----------- |
| CLEARTEXT | 1 |  |
| ZLIB | 2 |  |

<a name="emcclass.proto"/>
<p align="right"><a href="#top">Top</a></p>

## emcclass.proto

<a name="pb.EmcPose"/>
### EmcPose


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcPose.tran"/> tran | [PmCartesian](#pb.PmCartesian) | required |  |
| <a name="pb.EmcPose.a"/> a | [double](#double) | optional |  |
| <a name="pb.EmcPose.b"/> b | [double](#double) | optional |  |
| <a name="pb.EmcPose.c"/> c | [double](#double) | optional |  |
| <a name="pb.EmcPose.u"/> u | [double](#double) | optional |  |
| <a name="pb.EmcPose.v"/> v | [double](#double) | optional |  |
| <a name="pb.EmcPose.w"/> w | [double](#double) | optional |  |

<a name="pb.PmCartesian"/>
### PmCartesian


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.PmCartesian.x"/> x | [double](#double) | optional |  |
| <a name="pb.PmCartesian.y"/> y | [double](#double) | optional |  |
| <a name="pb.PmCartesian.z"/> z | [double](#double) | optional |  |


<a name="log.proto"/>
<p align="right"><a href="#top">Top</a></p>

## log.proto

<a name="pb.LogMessage"/>
### LogMessage


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.LogMessage.origin"/> origin | [MsgOrigin](#pb.MsgOrigin) | required |  |
| <a name="pb.LogMessage.pid"/> pid | [int32](#int32) | required |  |
| <a name="pb.LogMessage.level"/> level | [MsgLevel](#pb.MsgLevel) | required |  |
| <a name="pb.LogMessage.tag"/> tag | [string](#string) | required |  |
| <a name="pb.LogMessage.text"/> text | [string](#string) | required |  |


<a name="message.proto"/>
<p align="right"><a href="#top">Top</a></p>

## message.proto

<a name="pb.Container"/>
### Container


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Container.type"/> type | [ContainerType](#pb.ContainerType) | required |  |
| <a name="pb.Container.tsc"/> tsc | [sfixed64](#sfixed64) | optional |  |
| <a name="pb.Container.preview"/> preview | [Preview](#pb.Preview) | repeated |  |
| <a name="pb.Container.motcmd"/> motcmd | [MotionCommand](#pb.MotionCommand) | optional |  |
| <a name="pb.Container.motstat"/> motstat | [MotionStatus](#pb.MotionStatus) | optional |  |
| <a name="pb.Container.legacy_motcmd"/> legacy_motcmd | [bytes](#bytes) | optional |  |
| <a name="pb.Container.legacy_motstat"/> legacy_motstat | [bytes](#bytes) | optional |  |
| <a name="pb.Container.rtapi_message"/> rtapi_message | [RTAPI_Message](#pb.RTAPI_Message) | optional |  |
| <a name="pb.Container.task_reply"/> task_reply | [TaskReply](#pb.TaskReply) | optional |  |
| <a name="pb.Container.ticket_update"/> ticket_update | [TicketUpdate](#pb.TicketUpdate) | optional |  |
| <a name="pb.Container.syslog"/> syslog | [bytes](#bytes) | optional |  |
| <a name="pb.Container.legacy_nml"/> legacy_nml | [bytes](#bytes) | optional |  |
| <a name="pb.Container.legacy_motconfig"/> legacy_motconfig | [bytes](#bytes) | optional |  |
| <a name="pb.Container.tv_sec"/> tv_sec | [int32](#int32) | optional |  |
| <a name="pb.Container.tv_nsec"/> tv_nsec | [int32](#int32) | optional |  |
| <a name="pb.Container.topic"/> topic | [string](#string) | optional |  |
| <a name="pb.Container.reply_required"/> reply_required | [bool](#bool) | optional |  |
| <a name="pb.Container.interp_state"/> interp_state | [InterpreterStateType](#pb.InterpreterStateType) | optional |  |
| <a name="pb.Container.interp_name"/> interp_name | [string](#string) | optional |  |
| <a name="pb.Container.rsvp"/> rsvp | [int32](#int32) | optional |  |
| <a name="pb.Container.in_reply_to"/> in_reply_to | [ContainerType](#pb.ContainerType) | optional |  |
| <a name="pb.Container.rcs_status"/> rcs_status | [RCS_STATUS](#pb.RCS_STATUS) | optional |  |
| <a name="pb.Container.status"/> status | [StatusType](#pb.StatusType) | optional |  |
| <a name="pb.Container.serial"/> serial | [int32](#int32) | optional |  |
| <a name="pb.Container.reply_serial"/> reply_serial | [int32](#int32) | optional |  |
| <a name="pb.Container.ticket"/> ticket | [int32](#int32) | optional |  |
| <a name="pb.Container.reply_ticket"/> reply_ticket | [int32](#int32) | optional |  |
| <a name="pb.Container.sequence"/> sequence | [int32](#int32) | optional |  |
| <a name="pb.Container.credit"/> credit | [int32](#int32) | optional |  |
| <a name="pb.Container.line_number"/> line_number | [int32](#int32) | optional |  |
| <a name="pb.Container.name"/> name | [string](#string) | optional |  |
| <a name="pb.Container.note"/> note | [string](#string) | repeated |  |
| <a name="pb.Container.retcode"/> retcode | [int32](#int32) | optional |  |
| <a name="pb.Container.uuid"/> uuid | [bytes](#bytes) | optional |  |
| <a name="pb.Container.trace"/> trace | [bool](#bool) | optional |  |
| <a name="pb.Container.instance"/> instance | [int32](#int32) | optional |  |
| <a name="pb.Container.value"/> value | [Value](#pb.Value) | repeated |  |
| <a name="pb.Container.rtapicmd"/> rtapicmd | [RTAPICommand](#pb.RTAPICommand) | optional |  |
| <a name="pb.Container.service_announcement"/> service_announcement | [ServiceAnnouncement](#pb.ServiceAnnouncement) | repeated |  |
| <a name="pb.Container.comp"/> comp | [Component](#pb.Component) | repeated |  |
| <a name="pb.Container.pin"/> pin | [Pin](#pb.Pin) | repeated |  |
| <a name="pb.Container.signal"/> signal | [Signal](#pb.Signal) | repeated |  |
| <a name="pb.Container.param"/> param | [Param](#pb.Param) | repeated |  |
| <a name="pb.Container.thread"/> thread | [Thread](#pb.Thread) | repeated |  |
| <a name="pb.Container.ring"/> ring | [Ring](#pb.Ring) | repeated |  |
| <a name="pb.Container.group"/> group | [Group](#pb.Group) | repeated |  |
| <a name="pb.Container.member"/> member | [Member](#pb.Member) | repeated |  |
| <a name="pb.Container.function"/> function | [Function](#pb.Function) | repeated |  |
| <a name="pb.Container.pparams"/> pparams | [ProtocolParameters](#pb.ProtocolParameters) | optional |  |
| <a name="pb.Container.vtable"/> vtable | [Vtable](#pb.Vtable) | repeated |  |
| <a name="pb.Container.inst"/> inst | [Inst](#pb.Inst) | repeated |  |
| <a name="pb.Container.app"/> app | [Application](#pb.Application) | repeated |  |
| <a name="pb.Container.launcher"/> launcher | [Launcher](#pb.Launcher) | repeated |  |
| <a name="pb.Container.index"/> index | [int32](#int32) | optional |  |
| <a name="pb.Container.log_message"/> log_message | [LogMessage](#pb.LogMessage) | optional |  |
| <a name="pb.Container.tpexecute"/> tpexecute | [TaskPlanExecute](#pb.TaskPlanExecute) | optional |  |
| <a name="pb.Container.tpblockdelete"/> tpblockdelete | [TaskPlanBlockDelete](#pb.TaskPlanBlockDelete) | optional |  |
| <a name="pb.Container.tpoptionalstop"/> tpoptionalstop | [TaskPlanOptionalStop](#pb.TaskPlanOptionalStop) | optional |  |
| <a name="pb.Container.tpopen"/> tpopen | [TaskPlanOpen](#pb.TaskPlanOpen) | optional |  |
| <a name="pb.Container.taskplan_reply"/> taskplan_reply | [TaskPlanReply](#pb.TaskPlanReply) | optional |  |
| <a name="pb.Container.traj_set_g5x"/> traj_set_g5x | [Emc_Traj_Set_G5x](#pb.Emc_Traj_Set_G5x) | optional |  |
| <a name="pb.Container.traj_set_g92"/> traj_set_g92 | [Emc_Traj_Set_G92](#pb.Emc_Traj_Set_G92) | optional |  |
| <a name="pb.Container.traj_set_rotation"/> traj_set_rotation | [Emc_Traj_Set_Rotation](#pb.Emc_Traj_Set_Rotation) | optional |  |
| <a name="pb.Container.traj_linear_move"/> traj_linear_move | [Emc_Traj_Linear_Move](#pb.Emc_Traj_Linear_Move) | optional |  |
| <a name="pb.Container.traj_probe"/> traj_probe | [Emc_Traj_Probe](#pb.Emc_Traj_Probe) | optional |  |
| <a name="pb.Container.traj_circular_move"/> traj_circular_move | [Emc_Traj_Circular_Move](#pb.Emc_Traj_Circular_Move) | optional |  |
| <a name="pb.Container.traj_rigid_tap"/> traj_rigid_tap | [Emc_Traj_Rigid_Tap](#pb.Emc_Traj_Rigid_Tap) | optional |  |
| <a name="pb.Container.traj_set_term_cond"/> traj_set_term_cond | [Emc_Traj_Set_Term_Cond](#pb.Emc_Traj_Set_Term_Cond) | optional |  |
| <a name="pb.Container.traj_set_spindlesync"/> traj_set_spindlesync | [Emc_Traj_Set_Spindlesync](#pb.Emc_Traj_Set_Spindlesync) | optional |  |
| <a name="pb.Container.traj_delay"/> traj_delay | [Emc_Traj_Delay](#pb.Emc_Traj_Delay) | optional |  |
| <a name="pb.Container.spindle_on"/> spindle_on | [Emc_Spindle_On](#pb.Emc_Spindle_On) | optional |  |
| <a name="pb.Container.spindle_speed"/> spindle_speed | [Emc_Spindle_Speed](#pb.Emc_Spindle_Speed) | optional |  |
| <a name="pb.Container.spindle_orient"/> spindle_orient | [Emc_Spindle_Orient](#pb.Emc_Spindle_Orient) | optional |  |
| <a name="pb.Container.spindle_wait_orient_complete"/> spindle_wait_orient_complete | [Emc_Spindle_Wait_Orient_Complete](#pb.Emc_Spindle_Wait_Orient_Complete) | optional |  |
| <a name="pb.Container.tool_set_offet"/> tool_set_offet | [Emc_Tool_Set_Offset](#pb.Emc_Tool_Set_Offset) | optional |  |
| <a name="pb.Container.traj_set_offset"/> traj_set_offset | [Emc_Traj_Set_Offset](#pb.Emc_Traj_Set_Offset) | optional |  |
| <a name="pb.Container.tool_prepare"/> tool_prepare | [Emc_Tool_Prepare](#pb.Emc_Tool_Prepare) | optional |  |
| <a name="pb.Container.tool_set_number"/> tool_set_number | [Emc_Tool_Set_Number](#pb.Emc_Tool_Set_Number) | optional |  |
| <a name="pb.Container.traj_set_fo_enable"/> traj_set_fo_enable | [Emc_Traj_Set_Fo_Enable](#pb.Emc_Traj_Set_Fo_Enable) | optional |  |
| <a name="pb.Container.traj_set_so_enable"/> traj_set_so_enable | [Emc_Traj_Set_So_Enable](#pb.Emc_Traj_Set_So_Enable) | optional |  |
| <a name="pb.Container.traj_set_fh_enable"/> traj_set_fh_enable | [Emc_Traj_Set_Fh_Enable](#pb.Emc_Traj_Set_Fh_Enable) | optional |  |
| <a name="pb.Container.motion_adaptive"/> motion_adaptive | [Emc_Motion_Adaptive](#pb.Emc_Motion_Adaptive) | optional |  |
| <a name="pb.Container.operator_display"/> operator_display | [Emc_Operator_Display](#pb.Emc_Operator_Display) | optional |  |
| <a name="pb.Container.operator_text"/> operator_text | [Emc_Operator_Text](#pb.Emc_Operator_Text) | optional |  |
| <a name="pb.Container.operator_error"/> operator_error | [Emc_Operator_Error](#pb.Emc_Operator_Error) | optional |  |
| <a name="pb.Container.motion_set_dout"/> motion_set_dout | [Emc_Motion_Set_Dout](#pb.Emc_Motion_Set_Dout) | optional |  |
| <a name="pb.Container.motion_set_aout"/> motion_set_aout | [Emc_Motion_Set_Aout](#pb.Emc_Motion_Set_Aout) | optional |  |
| <a name="pb.Container.aux_input_wait"/> aux_input_wait | [Emc_Aux_Input_Wait](#pb.Emc_Aux_Input_Wait) | optional |  |
| <a name="pb.Container.exec_plugin_call"/> exec_plugin_call | [Emc_Exec_Plugin_Ca1l](#pb.Emc_Exec_Plugin_Ca1l) | optional |  |
| <a name="pb.Container.io_plugin_call"/> io_plugin_call | [Emc_Io_Plugin_Call](#pb.Emc_Io_Plugin_Call) | optional |  |
| <a name="pb.Container.emc_status_config"/> emc_status_config | [EmcStatusConfig](#pb.EmcStatusConfig) | optional |  |
| <a name="pb.Container.emc_status_motion"/> emc_status_motion | [EmcStatusMotion](#pb.EmcStatusMotion) | optional |  |
| <a name="pb.Container.emc_status_io"/> emc_status_io | [EmcStatusIo](#pb.EmcStatusIo) | optional |  |
| <a name="pb.Container.emc_status_task"/> emc_status_task | [EmcStatusTask](#pb.EmcStatusTask) | optional |  |
| <a name="pb.Container.emc_status_interp"/> emc_status_interp | [EmcStatusInterp](#pb.EmcStatusInterp) | optional |  |
| <a name="pb.Container.emc_command_params"/> emc_command_params | [EmcCommandParameters](#pb.EmcCommandParameters) | optional |  |
| <a name="pb.Container.key"/> key | [ParamKey](#pb.ParamKey) | repeated |  |


<a name="motcmds.proto"/>
<p align="right"><a href="#top">Top</a></p>

## motcmds.proto

<a name="pb.MotionCommand"/>
### MotionCommand


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.MotionCommand.command"/> command | [cmd_code_t](#pb.cmd_code_t) | required |  |
| <a name="pb.MotionCommand.commandNum"/> commandNum | [fixed32](#fixed32) | required |  |
| <a name="pb.MotionCommand.motor_offset"/> motor_offset | [double](#double) | optional |  |
| <a name="pb.MotionCommand.maxLimit"/> maxLimit | [double](#double) | optional |  |
| <a name="pb.MotionCommand.minLimit"/> minLimit | [double](#double) | optional |  |
| <a name="pb.MotionCommand.pos"/> pos | [EmcPose](#pb.EmcPose) | optional |  |
| <a name="pb.MotionCommand.center"/> center | [PmCartesian](#pb.PmCartesian) | optional |  |
| <a name="pb.MotionCommand.normal"/> normal | [PmCartesian](#pb.PmCartesian) | optional |  |
| <a name="pb.MotionCommand.turn"/> turn | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.vel"/> vel | [double](#double) | optional |  |
| <a name="pb.MotionCommand.ini_maxvel"/> ini_maxvel | [double](#double) | optional |  |
| <a name="pb.MotionCommand.motion_type"/> motion_type | [MotionType](#pb.MotionType) | optional |  |
| <a name="pb.MotionCommand.spindlesync"/> spindlesync | [double](#double) | optional |  |
| <a name="pb.MotionCommand.acc"/> acc | [double](#double) | optional |  |
| <a name="pb.MotionCommand.backlash"/> backlash | [double](#double) | optional |  |
| <a name="pb.MotionCommand.id"/> id | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.termCond"/> termCond | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.tolerance"/> tolerance | [double](#double) | optional |  |
| <a name="pb.MotionCommand.axis"/> axis | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.scale"/> scale | [double](#double) | optional |  |
| <a name="pb.MotionCommand.offset"/> offset | [double](#double) | optional |  |
| <a name="pb.MotionCommand.home"/> home | [double](#double) | optional |  |
| <a name="pb.MotionCommand.home_final_vel"/> home_final_vel | [double](#double) | optional |  |
| <a name="pb.MotionCommand.search_vel"/> search_vel | [double](#double) | optional |  |
| <a name="pb.MotionCommand.latch_vel"/> latch_vel | [double](#double) | optional |  |
| <a name="pb.MotionCommand.flags"/> flags | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.home_sequence"/> home_sequence | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.volatile_home"/> volatile_home | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.minFerror"/> minFerror | [double](#double) | optional |  |
| <a name="pb.MotionCommand.maxFerror"/> maxFerror | [double](#double) | optional |  |
| <a name="pb.MotionCommand.wdWait"/> wdWait | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.debug"/> debug | [fixed32](#fixed32) | optional |  |
| <a name="pb.MotionCommand.now"/> now | [int32](#int32) | optional |  |
| <a name="pb.MotionCommand.out"/> out | [int32](#int32) | optional |  |
| <a name="pb.MotionCommand.start"/> start | [int32](#int32) | optional |  |
| <a name="pb.MotionCommand.end"/> end | [int32](#int32) | optional |  |
| <a name="pb.MotionCommand.mode"/> mode | [int32](#int32) | optional |  |
| <a name="pb.MotionCommand.comp_nominal"/> comp_nominal | [double](#double) | optional |  |
| <a name="pb.MotionCommand.comp_forward"/> comp_forward | [double](#double) | optional |  |
| <a name="pb.MotionCommand.comp_reverse"/> comp_reverse | [double](#double) | optional |  |
| <a name="pb.MotionCommand.probe_type"/> probe_type | [int32](#int32) | optional |  |
| <a name="pb.MotionCommand.tool_offset"/> tool_offset | [EmcPose](#pb.EmcPose) | optional |  |

<a name="pb.MotionStatus"/>
### MotionStatus


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.MotionStatus.commandEcho"/> commandEcho | [cmd_code_t](#pb.cmd_code_t) | required |  |
| <a name="pb.MotionStatus.commandNumEcho"/> commandNumEcho | [fixed32](#fixed32) | required |  |
| <a name="pb.MotionStatus.commandStatus"/> commandStatus | [cmd_status_t](#pb.cmd_status_t) | required |  |
| <a name="pb.MotionStatus.carte_pos_fb"/> carte_pos_fb | [EmcPose](#pb.EmcPose) | optional |  |


<a name="pb.MotionType"/>
### MotionType


| Name | Number | Description |
| ---- | ------ | ----------- |
| _EMC_MOTION_TYPE_NONE | 0 |  |
| _EMC_MOTION_TYPE_TRAVERSE | 1 |  |
| _EMC_MOTION_TYPE_FEED | 2 |  |
| _EMC_MOTION_TYPE_ARC | 3 |  |
| _EMC_MOTION_TYPE_TOOLCHANGE | 4 |  |
| _EMC_MOTION_TYPE_PROBING | 5 |  |
| _EMC_MOTION_TYPE_INDEXROTARY | 6 |  |

<a name="pb.cmd_code_t"/>
### cmd_code_t


| Name | Number | Description |
| ---- | ------ | ----------- |
| EMCMOT_ABORT | 4000 |  |
| EMCMOT_AXIS_ABORT | 4001 |  |
| EMCMOT_ENABLE | 4002 |  |
| EMCMOT_DISABLE | 4003 |  |
| EMCMOT_ENABLE_AMPLIFIER | 4004 |  |
| EMCMOT_DISABLE_AMPLIFIER | 4005 |  |
| EMCMOT_ENABLE_WATCHDOG | 4006 |  |
| EMCMOT_DISABLE_WATCHDOG | 4007 |  |
| EMCMOT_ACTIVATE_JOINT | 4008 |  |
| EMCMOT_DEACTIVATE_JOINT | 4009 |  |
| EMCMOT_PAUSE | 4010 |  |
| EMCMOT_RESUME | 4011 |  |
| EMCMOT_STEP | 4012 |  |
| EMCMOT_FREE | 4013 |  |
| EMCMOT_COORD | 4014 |  |
| EMCMOT_TELEOP | 4015 |  |
| EMCMOT_SPINDLE_SCALE | 4016 |  |
| EMCMOT_SS_ENABLE | 4017 |  |
| EMCMOT_FEED_SCALE | 4018 |  |
| EMCMOT_FS_ENABLE | 4019 |  |
| EMCMOT_FH_ENABLE | 4020 |  |
| EMCMOT_AF_ENABLE | 4021 |  |
| EMCMOT_OVERRIDE_LIMITS | 4022 |  |
| EMCMOT_HOME | 4023 |  |
| EMCMOT_UNHOME | 4024 |  |
| EMCMOT_JOG_CONT | 4025 |  |
| EMCMOT_JOG_INCR | 4026 |  |
| EMCMOT_JOG_ABS | 4027 |  |
| EMCMOT_SET_LINE | 4028 |  |
| EMCMOT_SET_CIRCLE | 4029 |  |
| EMCMOT_SET_TELEOP_VECTOR | 4030 |  |
| EMCMOT_CLEAR_PROBE_FLAGS | 4031 |  |
| EMCMOT_PROBE | 4032 |  |
| EMCMOT_RIGID_TAP | 4033 |  |
| EMCMOT_SET_POSITION_LIMITS | 4034 |  |
| EMCMOT_SET_BACKLASH | 4035 |  |
| EMCMOT_SET_MIN_FERROR | 4036 |  |
| EMCMOT_SET_MAX_FERROR | 4037 |  |
| EMCMOT_SET_VEL | 4038 |  |
| EMCMOT_SET_VEL_LIMIT | 4039 |  |
| EMCMOT_SET_JOINT_VEL_LIMIT | 4040 |  |
| EMCMOT_SET_JOINT_ACC_LIMIT | 4041 |  |
| EMCMOT_SET_ACC | 4042 |  |
| EMCMOT_SET_TERM_COND | 4043 |  |
| EMCMOT_SET_NUM_AXES | 4044 |  |
| EMCMOT_SET_WORLD_HOME | 4045 |  |
| EMCMOT_SET_HOMING_PARAMS | 4046 |  |
| EMCMOT_SET_DEBUG | 4047 |  |
| EMCMOT_SET_DOUT | 4048 |  |
| EMCMOT_SET_AOUT | 4049 |  |
| EMCMOT_SET_SPINDLESYNC | 4050 |  |
| EMCMOT_SPINDLE_ON | 4051 |  |
| EMCMOT_SPINDLE_OFF | 4052 |  |
| EMCMOT_SPINDLE_INCREASE | 4053 |  |
| EMCMOT_SPINDLE_DECREASE | 4054 |  |
| EMCMOT_SPINDLE_BRAKE_ENGAGE | 4055 |  |
| EMCMOT_SPINDLE_BRAKE_RELEASE | 4056 |  |
| EMCMOT_SET_MOTOR_OFFSET | 4057 |  |
| EMCMOT_SET_JOINT_COMP | 4058 |  |
| EMCMOT_SET_OFFSET | 4059 |  |

<a name="pb.cmd_status_t"/>
### cmd_status_t


| Name | Number | Description |
| ---- | ------ | ----------- |
| EMCMOT_COMMAND_OK | 0 |  |
| EMCMOT_COMMAND_UNKNOWN_COMMAND | 1 |  |
| EMCMOT_COMMAND_INVALID_COMMAND | 2 |  |
| EMCMOT_COMMAND_INVALID_PARAMS | 3 |  |
| EMCMOT_COMMAND_BAD_EXEC | 4 |  |

<a name="nanopb.proto"/>
<p align="right"><a href="#top">Top</a></p>

## nanopb.proto

<a name="NanoPBOptions"/>
### NanoPBOptions


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="NanoPBOptions.max_size"/> max_size | [int32](#int32) | optional |  |
| <a name="NanoPBOptions.max_count"/> max_count | [int32](#int32) | optional |  |
| <a name="NanoPBOptions.int_size"/> int_size | [IntSize](#IntSize) | optional |  |
| <a name="NanoPBOptions.type"/> type | [FieldType](#FieldType) | optional |  |
| <a name="NanoPBOptions.long_names"/> long_names | [bool](#bool) | optional |  |
| <a name="NanoPBOptions.packed_struct"/> packed_struct | [bool](#bool) | optional |  |
| <a name="NanoPBOptions.skip_message"/> skip_message | [bool](#bool) | optional |  |
| <a name="NanoPBOptions.no_unions"/> no_unions | [bool](#bool) | optional |  |
| <a name="NanoPBOptions.msgid"/> msgid | [uint32](#uint32) | optional |  |


<a name="FieldType"/>
### FieldType


| Name | Number | Description |
| ---- | ------ | ----------- |
| FT_DEFAULT | 0 |  |
| FT_CALLBACK | 1 |  |
| FT_POINTER | 4 |  |
| FT_STATIC | 2 |  |
| FT_IGNORE | 3 |  |

<a name="IntSize"/>
### IntSize


| Name | Number | Description |
| ---- | ------ | ----------- |
| IS_DEFAULT | 0 |  |
| IS_8 | 8 |  |
| IS_16 | 16 |  |
| IS_32 | 32 |  |
| IS_64 | 64 |  |

<a name="object.proto"/>
<p align="right"><a href="#top">Top</a></p>

## object.proto

<a name="pb.AnError"/>
### AnError


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.AnError.error_code"/> error_code | [sfixed32](#sfixed32) | required |  |
| <a name="pb.AnError.severity"/> severity | [Severity](#pb.Severity) | optional |  |
| <a name="pb.AnError.error_text"/> error_text | [string](#string) | optional |  |
| <a name="pb.AnError.origin"/> origin | [Originator](#pb.Originator) | optional |  |

<a name="pb.Component"/>
### Component


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Component.name"/> name | [string](#string) | optional |  |
| <a name="pb.Component.ninst"/> ninst | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.comp_id"/> comp_id | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Component.type"/> type | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.state"/> state | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.last_update"/> last_update | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.last_bound"/> last_bound | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.last_unbound"/> last_unbound | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.pid"/> pid | [fixed32](#fixed32) | optional |  |
| <a name="pb.Component.args"/> args | [string](#string) | optional |  |
| <a name="pb.Component.timer"/> timer | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Component.userarg1"/> userarg1 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Component.userarg2"/> userarg2 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Component.pin"/> pin | [Pin](#pb.Pin) | repeated |  |
| <a name="pb.Component.param"/> param | [Param](#pb.Param) | repeated |  |
| <a name="pb.Component.no_create"/> no_create | [bool](#bool) | optional |  |

<a name="pb.Function"/>
### Function


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Function.name"/> name | [string](#string) | optional |  |
| <a name="pb.Function.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Function.owner_id"/> owner_id | [fixed32](#fixed32) | optional |  |
| <a name="pb.Function.users"/> users | [fixed32](#fixed32) | optional |  |
| <a name="pb.Function.runtime"/> runtime | [fixed32](#fixed32) | optional |  |
| <a name="pb.Function.maxtime"/> maxtime | [fixed32](#fixed32) | optional |  |
| <a name="pb.Function.reentrant"/> reentrant | [bool](#bool) | optional |  |

<a name="pb.Group"/>
### Group


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Group.name"/> name | [string](#string) | optional |  |
| <a name="pb.Group.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Group.userarg1"/> userarg1 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Group.userarg2"/> userarg2 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Group.refcount"/> refcount | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Group.member"/> member | [Member](#pb.Member) | repeated |  |

<a name="pb.Inst"/>
### Inst


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Inst.name"/> name | [string](#string) | optional |  |
| <a name="pb.Inst.comp_id"/> comp_id | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Inst.inst_id"/> inst_id | [fixed32](#fixed32) | optional |  |
| <a name="pb.Inst.inst_size"/> inst_size | [fixed32](#fixed32) | optional |  |
| <a name="pb.Inst.vtable"/> vtable | [fixed64](#fixed64) | optional |  |

<a name="pb.Instance"/>
### Instance


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Instance.name"/> name | [string](#string) | optional |  |
| <a name="pb.Instance.id"/> id | [sfixed32](#sfixed32) | optional |  |

<a name="pb.Member"/>
### Member


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Member.mtype"/> mtype | [ObjectType](#pb.ObjectType) | optional |  |
| <a name="pb.Member.userarg1"/> userarg1 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Member.epsilon"/> epsilon | [double](#double) | optional |  |
| <a name="pb.Member.signal"/> signal | [Signal](#pb.Signal) | optional |  |
| <a name="pb.Member.groupname"/> groupname | [string](#string) | optional |  |
| <a name="pb.Member.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Member.pin"/> pin | [Pin](#pb.Pin) | optional |  |
| <a name="pb.Member.param"/> param | [Param](#pb.Param) | optional |  |

<a name="pb.Originator"/>
### Originator


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Originator.origin"/> origin | [OriginType](#pb.OriginType) | optional |  |
| <a name="pb.Originator.detail"/> detail | [OriginDetail](#pb.OriginDetail) | optional |  |
| <a name="pb.Originator.name"/> name | [string](#string) | optional |  |
| <a name="pb.Originator.id"/> id | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Originator.instance"/> instance | [Instance](#pb.Instance) | optional |  |

<a name="pb.Param"/>
### Param


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Param.type"/> type | [ValueType](#pb.ValueType) | optional |  |
| <a name="pb.Param.name"/> name | [string](#string) | optional |  |
| <a name="pb.Param.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Param.halbit"/> halbit | [bool](#bool) | optional |  |
| <a name="pb.Param.halfloat"/> halfloat | [double](#double) | optional |  |
| <a name="pb.Param.hals32"/> hals32 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Param.halu32"/> halu32 | [fixed32](#fixed32) | optional |  |
| <a name="pb.Param.strval"/> strval | [string](#string) | optional |  |
| <a name="pb.Param.blob"/> blob | [bytes](#bytes) | optional |  |
| <a name="pb.Param.dir"/> dir | [HalParamDirection](#pb.HalParamDirection) | optional |  |
| <a name="pb.Param.oldname"/> oldname | [string](#string) | optional |  |
| <a name="pb.Param.owner"/> owner | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Param.runtime"/> runtime | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Param.maytime"/> maytime | [sfixed32](#sfixed32) | optional |  |

<a name="pb.Pin"/>
### Pin


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Pin.type"/> type | [ValueType](#pb.ValueType) | optional |  |
| <a name="pb.Pin.name"/> name | [string](#string) | optional |  |
| <a name="pb.Pin.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Pin.dir"/> dir | [HalPinDirection](#pb.HalPinDirection) | optional |  |
| <a name="pb.Pin.halbit"/> halbit | [bool](#bool) | optional |  |
| <a name="pb.Pin.halfloat"/> halfloat | [double](#double) | optional |  |
| <a name="pb.Pin.hals32"/> hals32 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Pin.halu32"/> halu32 | [fixed32](#fixed32) | optional |  |
| <a name="pb.Pin.owner"/> owner | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Pin.linked"/> linked | [bool](#bool) | optional |  |
| <a name="pb.Pin.oldname"/> oldname | [string](#string) | optional |  |
| <a name="pb.Pin.epsilon"/> epsilon | [double](#double) | optional |  |
| <a name="pb.Pin.flags"/> flags | [fixed32](#fixed32) | optional |  |

<a name="pb.ProtocolParameters"/>
### ProtocolParameters


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.ProtocolParameters.keepalive_timer"/> keepalive_timer | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.ProtocolParameters.group_timer"/> group_timer | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.ProtocolParameters.rcomp_timer"/> rcomp_timer | [sfixed32](#sfixed32) | optional |  |

<a name="pb.Ring"/>
### Ring


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Ring.name"/> name | [string](#string) | optional |  |
| <a name="pb.Ring.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Ring.owner"/> owner | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Ring.stream"/> stream | [bool](#bool) | optional |  |
| <a name="pb.Ring.wmutex"/> wmutex | [bool](#bool) | optional |  |
| <a name="pb.Ring.rmutex"/> rmutex | [bool](#bool) | optional |  |
| <a name="pb.Ring.rtapi_shm"/> rtapi_shm | [bool](#bool) | optional |  |
| <a name="pb.Ring.reader"/> reader | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Ring.writer"/> writer | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Ring.size"/> size | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Ring.scratchpad"/> scratchpad | [sfixed32](#sfixed32) | optional |  |

<a name="pb.ServiceAnnouncement"/>
### ServiceAnnouncement


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.ServiceAnnouncement.stype"/> stype | [ServiceType](#pb.ServiceType) | required |  |
| <a name="pb.ServiceAnnouncement.version"/> version | [fixed32](#fixed32) | required |  |
| <a name="pb.ServiceAnnouncement.instance"/> instance | [fixed32](#fixed32) | required |  |
| <a name="pb.ServiceAnnouncement.api"/> api | [ServiceAPI](#pb.ServiceAPI) | required |  |
| <a name="pb.ServiceAnnouncement.uri"/> uri | [string](#string) | required |  |
| <a name="pb.ServiceAnnouncement.description"/> description | [string](#string) | optional |  |

<a name="pb.Signal"/>
### Signal


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Signal.type"/> type | [ValueType](#pb.ValueType) | optional |  |
| <a name="pb.Signal.name"/> name | [string](#string) | optional |  |
| <a name="pb.Signal.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Signal.halbit"/> halbit | [bool](#bool) | optional |  |
| <a name="pb.Signal.halfloat"/> halfloat | [double](#double) | optional |  |
| <a name="pb.Signal.hals32"/> hals32 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Signal.halu32"/> halu32 | [fixed32](#fixed32) | optional |  |
| <a name="pb.Signal.strval"/> strval | [string](#string) | optional |  |
| <a name="pb.Signal.blob"/> blob | [bytes](#bytes) | optional |  |
| <a name="pb.Signal.readers"/> readers | [fixed32](#fixed32) | optional |  |
| <a name="pb.Signal.writers"/> writers | [fixed32](#fixed32) | optional |  |
| <a name="pb.Signal.bidirs"/> bidirs | [fixed32](#fixed32) | optional |  |

<a name="pb.Thread"/>
### Thread


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Thread.name"/> name | [string](#string) | optional |  |
| <a name="pb.Thread.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Thread.uses_fp"/> uses_fp | [bool](#bool) | optional |  |
| <a name="pb.Thread.period"/> period | [fixed32](#fixed32) | optional |  |
| <a name="pb.Thread.priority"/> priority | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Thread.task_id"/> task_id | [fixed32](#fixed32) | optional |  |
| <a name="pb.Thread.cpu_id"/> cpu_id | [fixed32](#fixed32) | optional |  |
| <a name="pb.Thread.function"/> function | [string](#string) | repeated |  |

<a name="pb.Vtable"/>
### Vtable


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Vtable.name"/> name | [string](#string) | optional |  |
| <a name="pb.Vtable.context"/> context | [fixed32](#fixed32) | optional |  |
| <a name="pb.Vtable.comp_id"/> comp_id | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Vtable.instance_id"/> instance_id | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Vtable.handle"/> handle | [fixed32](#fixed32) | optional |  |
| <a name="pb.Vtable.refcount"/> refcount | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Vtable.version"/> version | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Vtable.vtable"/> vtable | [fixed64](#fixed64) | optional |  |


<a name="param.proto"/>
<p align="right"><a href="#top">Top</a></p>

## param.proto

<a name="pb.ParamKey"/>
### ParamKey
A parameter key.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.ParamKey.type"/> type | [ParamType](#pb.ParamType) | optional | Type of the parameter value. |
| <a name="pb.ParamKey.name"/> name | [string](#string) | optional | Name of the key. |
| <a name="pb.ParamKey.paramstring"/> paramstring | [string](#string) | optional | String value. |
| <a name="pb.ParamKey.parambinary"/> parambinary | [bytes](#bytes) | optional | Binary value. |
| <a name="pb.ParamKey.paramint"/> paramint | [sfixed32](#sfixed32) | optional | Integer value. |
| <a name="pb.ParamKey.parambool"/> parambool | [bool](#bool) | optional | Boolean value. |
| <a name="pb.ParamKey.paramdouble"/> paramdouble | [double](#double) | optional | Floating point value. |
| <a name="pb.ParamKey.paramlist"/> paramlist | [ParamKey](#pb.ParamKey) | repeated | List value. |
| <a name="pb.ParamKey.meta"/> meta | [ParamKey](#pb.ParamKey) | repeated | Meta keys. |
| <a name="pb.ParamKey.deleted"/> deleted | [bool](#bool) | optional | Flags this key as deleted. |
| <a name="pb.ParamKey.readonly"/> readonly | [bool](#bool) | optional | Indicates that this key is read-only. |


<a name="pb.ParamType"/>
### ParamType
Parameter types.

| Name | Number | Description |
| ---- | ------ | ----------- |
| PARAM_STRING | 0 | String. |
| PARAM_BINARY | 1 | Binary data. |
| PARAM_INTEGER | 2 | 32 bit signed integer. |
| PARAM_BOOLEAN | 3 | Boolean. |
| PARAM_DOUBLE | 4 | Double. |
| PARAM_LIST | 5 | List of values. |

<a name="preview.proto"/>
<p align="right"><a href="#top">Top</a></p>

## preview.proto

<a name="pb.Position"/>
### Position


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Position.x"/> x | [double](#double) | optional |  |
| <a name="pb.Position.y"/> y | [double](#double) | optional |  |
| <a name="pb.Position.z"/> z | [double](#double) | optional |  |
| <a name="pb.Position.a"/> a | [double](#double) | optional |  |
| <a name="pb.Position.b"/> b | [double](#double) | optional |  |
| <a name="pb.Position.c"/> c | [double](#double) | optional |  |
| <a name="pb.Position.u"/> u | [double](#double) | optional |  |
| <a name="pb.Position.v"/> v | [double](#double) | optional |  |
| <a name="pb.Position.w"/> w | [double](#double) | optional |  |

<a name="pb.Preview"/>
### Preview


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Preview.type"/> type | [PreviewOpType](#pb.PreviewOpType) | required |  |
| <a name="pb.Preview.line_number"/> line_number | [int32](#int32) | optional |  |
| <a name="pb.Preview.pos"/> pos | [Position](#pb.Position) | optional |  |
| <a name="pb.Preview.first_end"/> first_end | [double](#double) | optional |  |
| <a name="pb.Preview.second_end"/> second_end | [double](#double) | optional |  |
| <a name="pb.Preview.first_axis"/> first_axis | [double](#double) | optional |  |
| <a name="pb.Preview.second_axis"/> second_axis | [double](#double) | optional |  |
| <a name="pb.Preview.rotation"/> rotation | [int32](#int32) | optional |  |
| <a name="pb.Preview.axis_end_point"/> axis_end_point | [double](#double) | optional |  |
| <a name="pb.Preview.xy_rotation"/> xy_rotation | [double](#double) | optional |  |
| <a name="pb.Preview.plane"/> plane | [int32](#int32) | optional |  |
| <a name="pb.Preview.rate"/> rate | [double](#double) | optional |  |
| <a name="pb.Preview.feed_mode"/> feed_mode | [int32](#int32) | optional |  |
| <a name="pb.Preview.time"/> time | [double](#double) | optional |  |
| <a name="pb.Preview.text"/> text | [string](#string) | optional |  |
| <a name="pb.Preview.angular_units"/> angular_units | [double](#double) | optional |  |
| <a name="pb.Preview.length_units"/> length_units | [double](#double) | optional |  |
| <a name="pb.Preview.probetype"/> probetype | [int32](#int32) | optional |  |
| <a name="pb.Preview.kins"/> kins | [KinematicsType](#pb.KinematicsType) | optional |  |
| <a name="pb.Preview.axismask"/> axismask | [int32](#int32) | optional |  |
| <a name="pb.Preview.g5_index"/> g5_index | [int32](#int32) | optional |  |
| <a name="pb.Preview.pocket"/> pocket | [int32](#int32) | optional |  |
| <a name="pb.Preview.stype"/> stype | [SourceType](#pb.SourceType) | optional |  |
| <a name="pb.Preview.filename"/> filename | [string](#string) | optional |  |
| <a name="pb.Preview.cmdstring"/> cmdstring | [string](#string) | optional |  |
| <a name="pb.Preview.call_level"/> call_level | [int32](#int32) | optional |  |


<a name="pb.KinematicsType"/>
### KinematicsType


| Name | Number | Description |
| ---- | ------ | ----------- |
| KT_JOINT | 1 |  |
| KT_TRIVKINS | 2 |  |
| KT_DELTA | 3 |  |

<a name="pb.PreviewOpType"/>
### PreviewOpType


| Name | Number | Description |
| ---- | ------ | ----------- |
| PV_STRAIGHT_PROBE | 1 |  |
| PV_RIGID_TAP | 2 |  |
| PV_STRAIGHT_FEED | 3 |  |
| PV_ARC_FEED | 4 |  |
| PV_STRAIGHT_TRAVERSE | 5 |  |
| PV_SET_G5X_OFFSET | 6 |  |
| PV_SET_G92_OFFSET | 7 |  |
| PV_SET_XY_ROTATION | 8 |  |
| PV_SELECT_PLANE | 9 |  |
| PV_SET_TRAVERSE_RATE | 10 |  |
| PV_SET_FEED_RATE | 11 |  |
| PV_CHANGE_TOOL | 12 |  |
| PV_CHANGE_TOOL_NUMBER | 13 |  |
| PV_DWELL | 14 |  |
| PV_MESSAGE | 15 |  |
| PV_COMMENT | 16 |  |
| PV_USE_TOOL_OFFSET | 17 |  |
| PV_SET_PARAMS | 18 |  |
| PV_SET_FEED_MODE | 19 |  |
| PV_SOURCE_CONTEXT | 20 |  |

<a name="pb.SourceType"/>
### SourceType


| Name | Number | Description |
| ---- | ------ | ----------- |
| ST_NGC_FILE | 1 |  |
| ST_NGC_STRING | 2 |  |
| ST_PYTHON_METHOD | 3 |  |

<a name="rtapi_message.proto"/>
<p align="right"><a href="#top">Top</a></p>

## rtapi_message.proto

<a name="pb.RTAPI_Message"/>
### RTAPI_Message


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.RTAPI_Message.msglevel"/> msglevel | [int32](#int32) | required |  |
| <a name="pb.RTAPI_Message.format"/> format | [string](#string) | required |  |
| <a name="pb.RTAPI_Message.arg"/> arg | [Value](#pb.Value) | repeated |  |


<a name="rtapicommand.proto"/>
<p align="right"><a href="#top">Top</a></p>

## rtapicommand.proto

<a name="pb.RTAPICommand"/>
### RTAPICommand


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.RTAPICommand.instance"/> instance | [int32](#int32) | required |  |
| <a name="pb.RTAPICommand.modname"/> modname | [string](#string) | optional |  |
| <a name="pb.RTAPICommand.rt_msglevel"/> rt_msglevel | [int32](#int32) | optional |  |
| <a name="pb.RTAPICommand.user_msglevel"/> user_msglevel | [int32](#int32) | optional |  |
| <a name="pb.RTAPICommand.argv"/> argv | [string](#string) | repeated |  |
| <a name="pb.RTAPICommand.threadname"/> threadname | [string](#string) | optional |  |
| <a name="pb.RTAPICommand.threadperiod"/> threadperiod | [int32](#int32) | optional |  |
| <a name="pb.RTAPICommand.use_fp"/> use_fp | [bool](#bool) | optional |  |
| <a name="pb.RTAPICommand.cpu"/> cpu | [int32](#int32) | optional |  |
| <a name="pb.RTAPICommand.comp"/> comp | [string](#string) | optional |  |
| <a name="pb.RTAPICommand.func"/> func | [string](#string) | optional |  |
| <a name="pb.RTAPICommand.instname"/> instname | [string](#string) | optional |  |
| <a name="pb.RTAPICommand.flags"/> flags | [int32](#int32) | optional |  |


<a name="status.proto"/>
<p align="right"><a href="#top">Top</a></p>

## status.proto

<a name="pb.EmcCommandParameters"/>
### EmcCommandParameters
EMC command parameters.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcCommandParameters.index"/> index | [uint32](#uint32) | optional | General purpose index. |
| <a name="pb.EmcCommandParameters.debug_level"/> debug_level | [uint32](#uint32) | optional | Debug level. |
| <a name="pb.EmcCommandParameters.line_number"/> line_number | [int32](#int32) | optional | General purpose line number. |
| <a name="pb.EmcCommandParameters.scale"/> scale | [double](#double) | optional | General purpose scale value. |
| <a name="pb.EmcCommandParameters.velocity"/> velocity | [double](#double) | optional | General purpose velocity value. |
| <a name="pb.EmcCommandParameters.distance"/> distance | [double](#double) | optional | General purpose distance value. |
| <a name="pb.EmcCommandParameters.value"/> value | [double](#double) | optional | General purpose value. |
| <a name="pb.EmcCommandParameters.enable"/> enable | [bool](#bool) | optional | General purpose enable value. |
| <a name="pb.EmcCommandParameters.command"/> command | [string](#string) | optional | General purpose command string. |
| <a name="pb.EmcCommandParameters.path"/> path | [string](#string) | optional | General purpose path string. |
| <a name="pb.EmcCommandParameters.task_mode"/> task_mode | [EmcTaskModeType](#pb.EmcTaskModeType) | optional | Task mode. |
| <a name="pb.EmcCommandParameters.task_state"/> task_state | [EmcTaskStateType](#pb.EmcTaskStateType) | optional | Task state. |
| <a name="pb.EmcCommandParameters.traj_mode"/> traj_mode | [EmcTrajectoryModeType](#pb.EmcTrajectoryModeType) | optional | Trajectory mode. |
| <a name="pb.EmcCommandParameters.pose"/> pose | [EmcPose](#pb.EmcPose) | optional | General purpose pose. |
| <a name="pb.EmcCommandParameters.tool_data"/> tool_data | [EmcToolData](#pb.EmcToolData) | optional | Tool data. |

<a name="pb.EmcProgramExtension"/>
### EmcProgramExtension
Program extension message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcProgramExtension.index"/> index | [int32](#int32) | required | Index of the program extension. |
| <a name="pb.EmcProgramExtension.extension"/> extension | [string](#string) | optional | Supported program extension. E.g. .gcode GCode program |

<a name="pb.EmcStatusAnalogIO"/>
### EmcStatusAnalogIO
Analog IO pin message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusAnalogIO.index"/> index | [int32](#int32) | required | Index of analog IO pin. |
| <a name="pb.EmcStatusAnalogIO.value"/> value | [double](#double) | optional | Current value of analog IO pin. |

<a name="pb.EmcStatusConfig"/>
### EmcStatusConfig
EMC status configuration message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusConfig.default_acceleration"/> default_acceleration | [double](#double) | optional | Default acceleration. Reflects parameter [TRAJ]DEFAULT_ACCELERATION. |
| <a name="pb.EmcStatusConfig.axes"/> axes | [int32](#int32) | optional | Number of axes. Reflects [TRAJ]AXES |
| <a name="pb.EmcStatusConfig.axis"/> axis | [EmcStatusConfigAxis](#pb.EmcStatusConfigAxis) | repeated | Per axis configuration values. |
| <a name="pb.EmcStatusConfig.axis_mask"/> axis_mask | [int32](#int32) | optional | Mask of axes. Reflects [TRAJ]COORDINATES and returns the sum of the axes X=1, Y=2, Z=4, A=8, B=16, C=32, U=64, V=128, W=256. |
| <a name="pb.EmcStatusConfig.cycle_time"/> cycle_time | [double](#double) | optional | Polling cycle time. Reflects [TRAJ]CYCLE_TIME |
| <a name="pb.EmcStatusConfig.debug"/> debug | [int32](#int32) | optional | Debug flag. |
| <a name="pb.EmcStatusConfig.kinematics_type"/> kinematics_type | [EmcKinematicsType](#pb.EmcKinematicsType) | optional | Kinematics type. |
| <a name="pb.EmcStatusConfig.max_acceleration"/> max_acceleration | [double](#double) | optional | Maximum acceleration. Reflects [TRAJ]MAX_ACCELERATION |
| <a name="pb.EmcStatusConfig.max_velocity"/> max_velocity | [double](#double) | optional | Maximum velocity. Reflects [TRAJ]MAX_VELOCITY |
| <a name="pb.EmcStatusConfig.linear_units"/> linear_units | [EmcLinearUnitsType](#pb.EmcLinearUnitsType) | optional | Linear machine units. Reflects [TRAJ]LINEAR_UNITS |
| <a name="pb.EmcStatusConfig.default_velocity"/> default_velocity | [double](#double) | optional | Default velocity. Reflects [TRAJ]DEFAULT_VELOCITY |
| <a name="pb.EmcStatusConfig.program_extension"/> program_extension | [EmcProgramExtension](#pb.EmcProgramExtension) | repeated | List if program supported program extensions. |
| <a name="pb.EmcStatusConfig.position_offset"/> position_offset | [EmcPositionOffsetType](#pb.EmcPositionOffsetType) | optional | Position offset type. Reflects [DISPLAY]POSITION_OFFSET |
| <a name="pb.EmcStatusConfig.position_feedback"/> position_feedback | [EmcPositionFeedbackType](#pb.EmcPositionFeedbackType) | optional | Position feedback type. Reflects [DISPLAY]POSITION_FEEDBACK |
| <a name="pb.EmcStatusConfig.max_feed_override"/> max_feed_override | [double](#double) | optional | Maximum feed override. Reflects [DISPLAY]MAX_FEED_OVERRIDE |
| <a name="pb.EmcStatusConfig.min_feed_override"/> min_feed_override | [double](#double) | optional | Minimum feed override. Reflects [DISPLAY]MIN_FEED_OVERRIDE |
| <a name="pb.EmcStatusConfig.max_spindle_override"/> max_spindle_override | [double](#double) | optional | Maximum spindle speed override. Reflects [DISPLAY]MAX_SPINDLE_OVERRIDE |
| <a name="pb.EmcStatusConfig.min_spindle_override"/> min_spindle_override | [double](#double) | optional | Minimum spindle override. Reflects [DISPLAY]MIN_SPINDLE_OVERRIDE |
| <a name="pb.EmcStatusConfig.default_spindle_speed"/> default_spindle_speed | [double](#double) | optional | Default spindle speed. Reflects [DISPLAY]DEFAULT_SPINDLE_SPEED |
| <a name="pb.EmcStatusConfig.default_linear_velocity"/> default_linear_velocity | [double](#double) | optional | Default linear velocity. Reflects [DISPLAY]DEFAULT_LINEAR_VELOCITY |
| <a name="pb.EmcStatusConfig.min_velocity"/> min_velocity | [double](#double) | optional | Minimum velocity override. Reflects [DISPLAY]MIN_VELOCITY |
| <a name="pb.EmcStatusConfig.max_linear_velocity"/> max_linear_velocity | [double](#double) | optional | Maximum linear velocity. Reflects [DISPLAY]MAX_LINEAR_VELOCITY |
| <a name="pb.EmcStatusConfig.min_linear_velocity"/> min_linear_velocity | [double](#double) | optional | Minimum linear velocity. Reflects [DISPLAY]MIN_LINEAR_VELOCITY |
| <a name="pb.EmcStatusConfig.default_angular_velocity"/> default_angular_velocity | [double](#double) | optional | Default angular velocity. Reflects [DISPLAY]DEFAULT_ANGULAR_VELOCITY |
| <a name="pb.EmcStatusConfig.max_angular_velocity"/> max_angular_velocity | [double](#double) | optional | Maximum angular velocity. Reflects [DISPLAY]MAX_ANGULAR_VELOCITY |
| <a name="pb.EmcStatusConfig.min_angular_velocity"/> min_angular_velocity | [double](#double) | optional | Minimum angular velocity. Reflects [DISPLAY]MIN_ANGULAR_VELOCITY |
| <a name="pb.EmcStatusConfig.increments"/> increments | [string](#string) | optional | White space separated jog increments. Reflects [DISPLAY]INCREMENTS |
| <a name="pb.EmcStatusConfig.grids"/> grids | [string](#string) | optional | Grid intervals. Reflects [DISPLAY]GRIDS |
| <a name="pb.EmcStatusConfig.lathe"/> lathe | [bool](#bool) | optional | Is machine a lathe. Reflects [DISPLAY]LATHE |
| <a name="pb.EmcStatusConfig.geometry"/> geometry | [string](#string) | optional | Geometry of machine. E.g. XYZ. Reflects [DISPLAY]GEOMETRY |
| <a name="pb.EmcStatusConfig.arcdivision"/> arcdivision | [uint32](#uint32) | optional | Display granularity for arcs. Reflects [DISPLAY]ARCDIVISION |
| <a name="pb.EmcStatusConfig.no_force_homing"/> no_force_homing | [bool](#bool) | optional | Do not enforce homing. Reflects [DISPLAY]NO_FORCE_HOMING |
| <a name="pb.EmcStatusConfig.remote_path"/> remote_path | [string](#string) | optional | Remote file path. Reflects [DISPLAY]PROGRAM_PREFIX |
| <a name="pb.EmcStatusConfig.time_units"/> time_units | [EmcTimeUnitsType](#pb.EmcTimeUnitsType) | optional | Time units type. Reflects [DISPLAY]TIME_UNITS |
| <a name="pb.EmcStatusConfig.name"/> name | [string](#string) | optional | Machine name. Reflects [EMC]MACHINE |
| <a name="pb.EmcStatusConfig.user_command"/> user_command | [EmcStatusUserCommand](#pb.EmcStatusUserCommand) | repeated | List of user commands. Reflects [DISPLAY]USER_COMMAND |
| <a name="pb.EmcStatusConfig.angular_units"/> angular_units | [EmcAngularUnitsType](#pb.EmcAngularUnitsType) | optional | Angular machine units. Reflects [TRAJ]ANGULAR_UNITS |

<a name="pb.EmcStatusConfigAxis"/>
### EmcStatusConfigAxis
Stores per axis information from configuration.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusConfigAxis.index"/> index | [int32](#int32) | required | Axis index. |
| <a name="pb.EmcStatusConfigAxis.axisType"/> axisType | [EmcAxisType](#pb.EmcAxisType) | optional | Type of axis. Reflects [AXIS_N]TYPE |
| <a name="pb.EmcStatusConfigAxis.backlash"/> backlash | [double](#double) | optional | Axis backlash. Reflects [AXIS_N]BACKLASH |
| <a name="pb.EmcStatusConfigAxis.max_ferror"/> max_ferror | [double](#double) | optional | Maximum following error. Reflects [AXIS_N]FERROR |
| <a name="pb.EmcStatusConfigAxis.max_position_limit"/> max_position_limit | [double](#double) | optional | Maximum position limit. Reflects [AXIS_N]MAX_LIMIT |
| <a name="pb.EmcStatusConfigAxis.min_ferror"/> min_ferror | [double](#double) | optional | Minimum following error. Reflects [AXIS_N]MIN_FERROR |
| <a name="pb.EmcStatusConfigAxis.min_position_limit"/> min_position_limit | [double](#double) | optional | Minimum position limit. Reflects [AXIS_N]MIN_LIMIT |
| <a name="pb.EmcStatusConfigAxis.home_sequence"/> home_sequence | [int32](#int32) | optional | Homing sequence index. Reflects [AXIS_N]HOME_SEQUENCE |
| <a name="pb.EmcStatusConfigAxis.max_acceleration"/> max_acceleration | [double](#double) | optional | Maximum acceleration. Reflects [AXIS_N]MAX_ACCELERATION |
| <a name="pb.EmcStatusConfigAxis.max_velocity"/> max_velocity | [double](#double) | optional | Maximum velocity. Reflects [AXIS_N]MAX_VELOCITY |
| <a name="pb.EmcStatusConfigAxis.increments"/> increments | [string](#string) | optional | Axis increments space separated.Reflects [AXIS_N]INCREMENTS or [DISPLAY]INCREMENTS |

<a name="pb.EmcStatusDigitalIO"/>
### EmcStatusDigitalIO
Digital IO pin message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusDigitalIO.index"/> index | [int32](#int32) | required | Index of digital IO pin. |
| <a name="pb.EmcStatusDigitalIO.value"/> value | [bool](#bool) | optional | Current value of digital IO pin. |

<a name="pb.EmcStatusGCode"/>
### EmcStatusGCode
Currently active GCodes message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusGCode.index"/> index | [int32](#int32) | required | Index of the GCode. |
| <a name="pb.EmcStatusGCode.value"/> value | [int32](#int32) | optional | GCode value. E.g. 210 for G21 |

<a name="pb.EmcStatusInterp"/>
### EmcStatusInterp
EMC status interpreter message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusInterp.command"/> command | [string](#string) | optional | Currently executing command. |
| <a name="pb.EmcStatusInterp.gcodes"/> gcodes | [EmcStatusGCode](#pb.EmcStatusGCode) | repeated | Currently active GCodes. |
| <a name="pb.EmcStatusInterp.interp_state"/> interp_state | [EmcInterpStateType](#pb.EmcInterpStateType) | optional | Current state of RS274NGC interpreter. |
| <a name="pb.EmcStatusInterp.interpreter_errcode"/> interpreter_errcode | [EmcInterpExitCodeType](#pb.EmcInterpExitCodeType) | optional | Current RS274NGC interpreter return code. |
| <a name="pb.EmcStatusInterp.mcodes"/> mcodes | [EmcStatusMCode](#pb.EmcStatusMCode) | repeated | Currently active MCodes. |
| <a name="pb.EmcStatusInterp.settings"/> settings | [EmcStatusSetting](#pb.EmcStatusSetting) | repeated | Current interpreter settings. [0] = sequence number, [1] = feed rate, [2] = velocity |
| <a name="pb.EmcStatusInterp.program_units"/> program_units | [EmcCanonUnitsType](#pb.EmcCanonUnitsType) | optional | Current interpreter program units. |

<a name="pb.EmcStatusIo"/>
### EmcStatusIo
EMC IO message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusIo.estop"/> estop | [bool](#bool) | optional | Estop active. |
| <a name="pb.EmcStatusIo.flood"/> flood | [bool](#bool) | optional | Flood enabled. |
| <a name="pb.EmcStatusIo.lube"/> lube | [bool](#bool) | optional | Lube enabled. |
| <a name="pb.EmcStatusIo.lube_level"/> lube_level | [bool](#bool) | optional | Lube level. Reflects iocontrol.0.lube_level |
| <a name="pb.EmcStatusIo.mist"/> mist | [bool](#bool) | optional | Mist enabled. |
| <a name="pb.EmcStatusIo.pocket_prepped"/> pocket_prepped | [bool](#bool) | optional | A Tx command completed and this pocket is prepared. TODO wrong type? |
| <a name="pb.EmcStatusIo.tool_in_spindle"/> tool_in_spindle | [bool](#bool) | optional | Current tool number. |
| <a name="pb.EmcStatusIo.tool_offset"/> tool_offset | [Position](#pb.Position) | optional | Offset values of the current tool. |
| <a name="pb.EmcStatusIo.tool_table"/> tool_table | [EmcToolData](#pb.EmcToolData) | repeated | List of tool entries. |

<a name="pb.EmcStatusLimit"/>
### EmcStatusLimit
Limit mask message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusLimit.index"/> index | [int32](#int32) | required | Axis index. |
| <a name="pb.EmcStatusLimit.value"/> value | [int32](#int32) | optional | Axis limit mask. minHardLimit=1, maxHardLimit=2, minSoftLimit=4, maxSoftLimit=8 |

<a name="pb.EmcStatusMCode"/>
### EmcStatusMCode
Currently active MCodes message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusMCode.index"/> index | [int32](#int32) | required | Index of MCode. |
| <a name="pb.EmcStatusMCode.value"/> value | [int32](#int32) | optional | MCode value. E.g. 100 for M100 |

<a name="pb.EmcStatusMotion"/>
### EmcStatusMotion
EMC status motion message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusMotion.active_queue"/> active_queue | [int32](#int32) | optional | Number of motions blending. |
| <a name="pb.EmcStatusMotion.actual_position"/> actual_position | [Position](#pb.Position) | optional | Current trajectory position. |
| <a name="pb.EmcStatusMotion.adaptive_feed_enabled"/> adaptive_feed_enabled | [bool](#bool) | optional | Status of adaptive feed override. |
| <a name="pb.EmcStatusMotion.ain"/> ain | [EmcStatusAnalogIO](#pb.EmcStatusAnalogIO) | repeated | Status of analog input pins. |
| <a name="pb.EmcStatusMotion.aout"/> aout | [EmcStatusAnalogIO](#pb.EmcStatusAnalogIO) | repeated | Status of analog output pins. |
| <a name="pb.EmcStatusMotion.axis"/> axis | [EmcStatusMotionAxis](#pb.EmcStatusMotionAxis) | repeated | Per axis motion values. |
| <a name="pb.EmcStatusMotion.block_delete"/> block_delete | [bool](#bool) | optional | Block delete on or off. |
| <a name="pb.EmcStatusMotion.current_line"/> current_line | [int32](#int32) | optional | Currently executing line. |
| <a name="pb.EmcStatusMotion.current_vel"/> current_vel | [double](#double) | optional | Current velocity in Cartesian space. |
| <a name="pb.EmcStatusMotion.delay_left"/> delay_left | [double](#double) | optional | Remaining time on dwell (G4) command. |
| <a name="pb.EmcStatusMotion.din"/> din | [EmcStatusDigitalIO](#pb.EmcStatusDigitalIO) | repeated | Status of digital input pins. |
| <a name="pb.EmcStatusMotion.distance_to_go"/> distance_to_go | [double](#double) | optional | Remaining distance of current move reported by trajectory planner. |
| <a name="pb.EmcStatusMotion.dout"/> dout | [EmcStatusDigitalIO](#pb.EmcStatusDigitalIO) | repeated | Status of digital output pins. |
| <a name="pb.EmcStatusMotion.dtg"/> dtg | [Position](#pb.Position) | optional | Remaining distance of current move reported by trajectory planner. |
| <a name="pb.EmcStatusMotion.enabled"/> enabled | [bool](#bool) | optional | Trajectory planner enabled flag. |
| <a name="pb.EmcStatusMotion.feed_hold_enabled"/> feed_hold_enabled | [bool](#bool) | optional | Enable flag for feed hold. |
| <a name="pb.EmcStatusMotion.feed_override_enabled"/> feed_override_enabled | [bool](#bool) | optional | Enable flag for feed override. |
| <a name="pb.EmcStatusMotion.feedrate"/> feedrate | [double](#double) | optional | Current feedrate override. |
| <a name="pb.EmcStatusMotion.g5x_index"/> g5x_index | [OriginIndex](#pb.OriginIndex) | optional | Currently active coordinate system. |
| <a name="pb.EmcStatusMotion.g5x_offset"/> g5x_offset | [Position](#pb.Position) | optional | Offset of the currently active coordinate system. |
| <a name="pb.EmcStatusMotion.g92_offset"/> g92_offset | [Position](#pb.Position) | optional | Current G92 offset. |
| <a name="pb.EmcStatusMotion.id"/> id | [int32](#int32) | optional | Currently executing motion id. |
| <a name="pb.EmcStatusMotion.inpos"/> inpos | [bool](#bool) | optional | Machine in position flag. |
| <a name="pb.EmcStatusMotion.joint_actual_position"/> joint_actual_position | [Position](#pb.Position) | optional | Actual joint position. |
| <a name="pb.EmcStatusMotion.joint_position"/> joint_position | [Position](#pb.Position) | optional | Desired joint position. |
| <a name="pb.EmcStatusMotion.limit"/> limit | [EmcStatusLimit](#pb.EmcStatusLimit) | repeated | Axis limit masks. |
| <a name="pb.EmcStatusMotion.motion_line"/> motion_line | [int32](#int32) | optional | Source line number motion is currently executing. Relation to id is unclear. |
| <a name="pb.EmcStatusMotion.motion_type"/> motion_type | [MotionType](#pb.MotionType) | optional | Trajectory planner mode. |
| <a name="pb.EmcStatusMotion.motion_mode"/> motion_mode | [EmcTrajectoryModeType](#pb.EmcTrajectoryModeType) | optional | Trajectory mode. |
| <a name="pb.EmcStatusMotion.paused"/> paused | [bool](#bool) | optional | Motion paused flag. |
| <a name="pb.EmcStatusMotion.position"/> position | [Position](#pb.Position) | optional | Trajectory position. |
| <a name="pb.EmcStatusMotion.probe_tripped"/> probe_tripped | [bool](#bool) | optional | True if probe has tripped. |
| <a name="pb.EmcStatusMotion.probe_val"/> probe_val | [int32](#int32) | optional | Reflects the value of the motion.probe-input pin |
| <a name="pb.EmcStatusMotion.probed_position"/> probed_position | [Position](#pb.Position) | optional | Position where probe has tripped |
| <a name="pb.EmcStatusMotion.probing"/> probing | [bool](#bool) | optional | Probe operation in progress. |
| <a name="pb.EmcStatusMotion.queue"/> queue | [int32](#int32) | optional | Current size of trajectory planner queue. |
| <a name="pb.EmcStatusMotion.queue_full"/> queue_full | [bool](#bool) | optional | Trajectory planner queue is full. |
| <a name="pb.EmcStatusMotion.rotation_xy"/> rotation_xy | [double](#double) | optional | Current XY rotation around Z axis. |
| <a name="pb.EmcStatusMotion.spindle_brake"/> spindle_brake | [bool](#bool) | optional | Spindle braked. |
| <a name="pb.EmcStatusMotion.spindle_direction"/> spindle_direction | [int32](#int32) | optional | Rotational direction of the spindle. forward=1, reverse=-1. |
| <a name="pb.EmcStatusMotion.spindle_enabled"/> spindle_enabled | [bool](#bool) | optional | Spindle enabled. |
| <a name="pb.EmcStatusMotion.spindle_increasing"/> spindle_increasing | [int32](#int32) | optional | Spindle speed is increasing. |
| <a name="pb.EmcStatusMotion.spindle_override_enabled"/> spindle_override_enabled | [bool](#bool) | optional | Spindle override is enabled. |
| <a name="pb.EmcStatusMotion.spindle_speed"/> spindle_speed | [double](#double) | optional | Spindle speed value in rpm. &gt; 0 is clockwise, &lt; 0 is counterclockwise |
| <a name="pb.EmcStatusMotion.spindlerate"/> spindlerate | [double](#double) | optional | Spindle speed override. |
| <a name="pb.EmcStatusMotion.state"/> state | [RCS_STATUS](#pb.RCS_STATUS) | optional | Current command execution status. |
| <a name="pb.EmcStatusMotion.max_velocity"/> max_velocity | [double](#double) | optional | Maximum velocity override. |
| <a name="pb.EmcStatusMotion.max_acceleration"/> max_acceleration | [double](#double) | optional | TODO remove |

<a name="pb.EmcStatusMotionAxis"/>
### EmcStatusMotionAxis
Stores per axis information from motion.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusMotionAxis.index"/> index | [int32](#int32) | required | Axis index. |
| <a name="pb.EmcStatusMotionAxis.enabled"/> enabled | [bool](#bool) | optional | Axis is enabled. |
| <a name="pb.EmcStatusMotionAxis.fault"/> fault | [bool](#bool) | optional | Axis amp fault. |
| <a name="pb.EmcStatusMotionAxis.ferror_current"/> ferror_current | [double](#double) | optional | Current following error. |
| <a name="pb.EmcStatusMotionAxis.ferror_highmark"/> ferror_highmark | [double](#double) | optional | Magnitude of maximum following error. |
| <a name="pb.EmcStatusMotionAxis.homed"/> homed | [bool](#bool) | optional | Axis has been homed. |
| <a name="pb.EmcStatusMotionAxis.homing"/> homing | [bool](#bool) | optional | Homing currently progress. |
| <a name="pb.EmcStatusMotionAxis.inpos"/> inpos | [bool](#bool) | optional | Axis is in position. |
| <a name="pb.EmcStatusMotionAxis.input"/> input | [double](#double) | optional | Current input position. |
| <a name="pb.EmcStatusMotionAxis.max_hard_limit"/> max_hard_limit | [bool](#bool) | optional | Maximum hard limit exceeded. |
| <a name="pb.EmcStatusMotionAxis.max_soft_limit"/> max_soft_limit | [bool](#bool) | optional | Maximum position limit was exceeded. |
| <a name="pb.EmcStatusMotionAxis.min_hard_limit"/> min_hard_limit | [bool](#bool) | optional | Minimum hard limit was exceeded. |
| <a name="pb.EmcStatusMotionAxis.min_soft_limit"/> min_soft_limit | [bool](#bool) | optional | Minimum position limit was exceeded. |
| <a name="pb.EmcStatusMotionAxis.output"/> output | [double](#double) | optional | Commanded output position. |
| <a name="pb.EmcStatusMotionAxis.override_limits"/> override_limits | [bool](#bool) | optional | Limits are overridden. |
| <a name="pb.EmcStatusMotionAxis.velocity"/> velocity | [double](#double) | optional | Current velocity. |

<a name="pb.EmcStatusSetting"/>
### EmcStatusSetting
Interpreter setting message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusSetting.index"/> index | [int32](#int32) | required | Index of interpreter setting. |
| <a name="pb.EmcStatusSetting.value"/> value | [double](#double) | optional | Interpreter settings value. |

<a name="pb.EmcStatusTask"/>
### EmcStatusTask
EMC status task message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusTask.echo_serial_number"/> echo_serial_number | [int32](#int32) | optional | The serial number of the last executed command set by a UI to task.All commands carry a serial number. Once the command has been executed,its serial number is reflected in echo_serial_number. |
| <a name="pb.EmcStatusTask.exec_state"/> exec_state | [EmcTaskExecStateType](#pb.EmcTaskExecStateType) | optional | Task execution state. |
| <a name="pb.EmcStatusTask.file"/> file | [string](#string) | optional | Currently executing gcode file. |
| <a name="pb.EmcStatusTask.input_timeout"/> input_timeout | [bool](#bool) | optional | Flag for M66 timer in progress. |
| <a name="pb.EmcStatusTask.optional_stop"/> optional_stop | [bool](#bool) | optional | Optional stop enabled. |
| <a name="pb.EmcStatusTask.read_line"/> read_line | [int32](#int32) | optional | Line the RS274NGC interpreter is currently reading. TODO move to interp |
| <a name="pb.EmcStatusTask.task_mode"/> task_mode | [EmcTaskModeType](#pb.EmcTaskModeType) | optional | Current task mode. |
| <a name="pb.EmcStatusTask.task_paused"/> task_paused | [int32](#int32) | optional | Task paused. |
| <a name="pb.EmcStatusTask.task_state"/> task_state | [EmcTaskStateType](#pb.EmcTaskStateType) | optional | Current task state. |
| <a name="pb.EmcStatusTask.total_lines"/> total_lines | [int32](#int32) | optional | Total number of lines of currently active program file. |

<a name="pb.EmcStatusUserCommand"/>
### EmcStatusUserCommand
User command message.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcStatusUserCommand.index"/> index | [int32](#int32) | required | User command index. |
| <a name="pb.EmcStatusUserCommand.command"/> command | [string](#string) | optional | User command separated by semicolon. E.g. G1A20;G1A0 Remove Filament. |

<a name="pb.EmcToolData"/>
### EmcToolData
Tool table data.

| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.EmcToolData.index"/> index | [int32](#int32) | required | Tool table index (not tool id). |
| <a name="pb.EmcToolData.id"/> id | [int32](#int32) | optional | ID/number of the tool. |
| <a name="pb.EmcToolData.diameter"/> diameter | [double](#double) | optional | Diameter of the tool. |
| <a name="pb.EmcToolData.frontangle"/> frontangle | [double](#double) | optional | Front angle of the tool (only on lathe). |
| <a name="pb.EmcToolData.backangle"/> backangle | [double](#double) | optional | Back angle of the tool (only on lathe). |
| <a name="pb.EmcToolData.orientation"/> orientation | [int32](#int32) | optional | Orientation of the tool (lathe only, 0-9). |
| <a name="pb.EmcToolData.offset"/> offset | [Position](#pb.Position) | optional | Position offset of the tool. |


<a name="pb.EmcAngularUnitsType"/>
### EmcAngularUnitsType
Types for EMC angular units.

| Name | Number | Description |
| ---- | ------ | ----------- |
| ANGULAR_UNITS_DEGREES | 1 | Degrees. |
| ANGULAR_UNITS_RADIAN | 2 | Radian. |
| ANGULAR_UNITS_GRAD | 3 | Grad. |

<a name="pb.EmcAxisType"/>
### EmcAxisType
Axis types.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_AXIS_LINEAR | 1 | Axis is using linear units. |
| EMC_AXIS_ANGULAR | 2 | Axis is using angular units. |

<a name="pb.EmcCanonUnitsType"/>
### EmcCanonUnitsType
Types for EMC Canon units.

| Name | Number | Description |
| ---- | ------ | ----------- |
| CANON_UNITS_INCHES | 1 | Inches. |
| CANON_UNITS_MM | 2 | Millimeters. |
| CANON_UNITS_CM | 3 | Centimeters. |

<a name="pb.EmcInterpExitCodeType"/>
### EmcInterpExitCodeType
Types for EMC interpreter exit codes.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_INTERP_EXIT_OK | 0 | Interpreter exited successfully. |
| EMC_INTERP_EXIT_EXIT | 1 | Interpreter exited with no status information. |
| EMC_INTERP_EXIT_EXECUTE_FINISH | 2 | Interpreter execution finished. |
| EMC_INTERP_EXIT_ENDFILE | 3 | Interpreter has reached end of file. |
| EMC_INTERP_EXIT_FILE_NOT_OPEN | 4 | Interpreter could not open the file. |
| EMC_INTERP_EXIT_ERROR | 5 | Interpreter exited with an error. |

<a name="pb.EmcInterpStateType"/>
### EmcInterpStateType
Types for EMC task interpreter state.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_TASK_INTERP_IDLE | 1 | Task interpreter is idling. |
| EMC_TASK_INTERP_READING | 2 | Task interpreter is reading. |
| EMC_TASK_INTERP_PAUSED | 3 | Task interpreter is paused. |
| EMC_TASK_INTERP_WAITING | 4 | Task interpreter is waiting. |

<a name="pb.EmcKinematicsType"/>
### EmcKinematicsType
EMC kinematics type.

| Name | Number | Description |
| ---- | ------ | ----------- |
| KINEMATICS_IDENTITY | 1 | Identity kinematics. |
| KINEMATICS_FORWARD_ONLY | 2 | Forward only kinematics. |
| KINEMATICS_INVERSE_ONLY | 3 | Inverse only kinematics. |
| KINEMATICS_BOTH | 4 | Forward and inverse kinematics. |

<a name="pb.EmcLinearUnitsType"/>
### EmcLinearUnitsType
Types for EMC linear units.

| Name | Number | Description |
| ---- | ------ | ----------- |
| LINEAR_UNITS_INCHES | 1 | Inches. |
| LINEAR_UNITS_MM | 2 | Millimeters. |
| LINEAR_UNITS_CM | 3 | Centimeters. |

<a name="pb.EmcPositionFeedbackType"/>
### EmcPositionFeedbackType
Position feedback types.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_CONFIG_ACTUAL_FEEDBACK | 1 | Feed back current position. |
| EMC_CONFIG_COMMANDED_FEEDBACK | 2 | Feed back commanded position. |

<a name="pb.EmcPositionOffsetType"/>
### EmcPositionOffsetType
Position offset types.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_CONFIG_RELATIVE_OFFSET | 1 | Offset in relative coordinates. |
| EMC_CONFIG_MACHINE_OFFSET | 2 | Offset in machine coordinates. |

<a name="pb.EmcTaskExecStateType"/>
### EmcTaskExecStateType
Types for EMC task execution state.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_TASK_EXEC_ERROR | 1 | Error during task execution. |
| EMC_TASK_EXEC_DONE | 2 | Task execution has bee completed. |
| EMC_TASK_EXEC_WAITING_FOR_MOTION | 3 | Task execution is waiting for Motion. |
| EMC_TASK_EXEC_WAITING_FOR_MOTION_QUEUE | 4 | Task execution is waiting for Motion queue. |
| EMC_TASK_EXEC_WAITING_FOR_IO | 5 | Task execution is waiting for IO. |
| EMC_TASK_EXEC_WAITING_FOR_MOTION_AND_IO | 7 | Task execution is waiting for Motion and IO. |
| EMC_TASK_EXEC_WAITING_FOR_DELAY | 8 | Task execution is waiting for a delay. |
| EMC_TASK_EXEC_WAITING_FOR_SYSTEM_CMD | 9 | Task execution is waiting for a system command. |
| EMC_TASK_EXEC_WAITING_FOR_SPINDLE_ORIENTED | 10 | Task execution is waiting for spindle orientation to complete. |

<a name="pb.EmcTaskModeType"/>
### EmcTaskModeType
Types for EMC task modes.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_TASK_MODE_MANUAL | 1 | Manual task mode. For example jogging. |
| EMC_TASK_MODE_AUTO | 2 | Automatic task mode. For example program execution. |
| EMC_TASK_MODE_MDI | 3 | MDI task mode. MDI commands only. |

<a name="pb.EmcTaskStateType"/>
### EmcTaskStateType
Types for EMC task state.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_TASK_STATE_ESTOP | 1 | Task is in ESTOP. |
| EMC_TASK_STATE_ESTOP_RESET | 2 | Task is trying to reset an ESTOP. |
| EMC_TASK_STATE_OFF | 3 | Task is turned off (no ESTOP) |
| EMC_TASK_STATE_ON | 4 | Task is turned on. |

<a name="pb.EmcTimeUnitsType"/>
### EmcTimeUnitsType
Types for EMC time units.

| Name | Number | Description |
| ---- | ------ | ----------- |
| TIME_UNITS_MINUTE | 1 | Minutes. |
| TIME_UNITS_SECOND | 2 | Seconds. |

<a name="pb.EmcTrajectoryModeType"/>
### EmcTrajectoryModeType
Types for trajectory motion control.

| Name | Number | Description |
| ---- | ------ | ----------- |
| EMC_TRAJ_MODE_FREE | 1 | Independent axis motion. |
| EMC_TRAJ_MODE_COORD | 2 | Coordinated axis motion. |
| EMC_TRAJ_MODE_TELEOP | 3 | Velocity based world coordinates motion. |

<a name="task.proto"/>
<p align="right"><a href="#top">Top</a></p>

## task.proto

<a name="pb.TaskPlanBlockDelete"/>
### TaskPlanBlockDelete


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TaskPlanBlockDelete.state"/> state | [bool](#bool) | required |  |

<a name="pb.TaskPlanExecute"/>
### TaskPlanExecute


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TaskPlanExecute.command"/> command | [string](#string) | optional |  |
| <a name="pb.TaskPlanExecute.line"/> line | [sfixed32](#sfixed32) | optional |  |

<a name="pb.TaskPlanOpen"/>
### TaskPlanOpen


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TaskPlanOpen.filename"/> filename | [string](#string) | required |  |

<a name="pb.TaskPlanOptionalStop"/>
### TaskPlanOptionalStop


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TaskPlanOptionalStop.state"/> state | [bool](#bool) | required |  |

<a name="pb.TaskPlanReply"/>
### TaskPlanReply


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TaskPlanReply.cmd"/> cmd | [ContainerType](#pb.ContainerType) | required |  |
| <a name="pb.TaskPlanReply.errormsg"/> errormsg | [string](#string) | optional |  |

<a name="pb.TaskReply"/>
### TaskReply


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TaskReply.ticket"/> ticket | [fixed32](#fixed32) | required |  |

<a name="pb.TicketUpdate"/>
### TicketUpdate


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.TicketUpdate.cticket"/> cticket | [fixed32](#fixed32) | required |  |
| <a name="pb.TicketUpdate.status"/> status | [RCS_STATUS](#pb.RCS_STATUS) | required |  |
| <a name="pb.TicketUpdate.text"/> text | [string](#string) | optional |  |


<a name="test.proto"/>
<p align="right"><a href="#top">Top</a></p>

## test.proto

<a name="pb.Test1"/>
### Test1


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Test1.op"/> op | [TestOpType](#pb.TestOpType) | required |  |
| <a name="pb.Test1.end"/> end | [EmcPose](#pb.EmcPose) | required |  |
| <a name="pb.Test1.center"/> center | [PmCartesian](#pb.PmCartesian) | optional |  |
| <a name="pb.Test1.normal"/> normal | [PmCartesian](#pb.PmCartesian) | optional |  |
| <a name="pb.Test1.turn"/> turn | [int32](#int32) | optional |  |

<a name="pb.Test2"/>
### Test2


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |

<a name="pb.Test3"/>
### Test3


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |


<a name="pb.TestOpType"/>
### TestOpType


| Name | Number | Description |
| ---- | ------ | ----------- |
| LINE | 10 |  |
| CIRCLE | 20 |  |

<a name="types.proto"/>
<p align="right"><a href="#top">Top</a></p>

## types.proto


<a name="pb.CanonDirection"/>
### CanonDirection


| Name | Number | Description |
| ---- | ------ | ----------- |
| _CANON_STOPPED | 1 |  |
| _CANON_CLOCKWISE | 2 |  |
| _CANON_COUNTERCLOCKWISE | 3 |  |

<a name="pb.ContainerType"/>
### ContainerType


| Name | Number | Description |
| ---- | ------ | ----------- |
| MT_RTMESSAGE | 2 |  |
| MT_MOTCMD | 3 |  |
| MT_MOTSTATUS | 4 |  |
| MT_LEGACY_MOTCMD | 5 |  |
| MT_LEGACY_MOTSTATUS | 6 |  |
| MT_WOU | 7 |  |
| MT_HALUPDATE | 8 |  |
| MT_RTAPI_MESSAGE | 9 |  |
| MT_LOG_MESSAGE | 10 |  |
| MT_PREVIEW | 11 |  |
| MT_PROGRESS | 12 |  |
| MT_INTERP_STAT | 13 |  |
| MT_SYSLOG | 18 |  |
| MT_LEGACY_NML | 19 |  |
| MT_LEGACY_MOTCONFIG | 20 |  |
| MT_STP_UPDATE_FULL | 26 |  |
| MT_STP_UPDATE | 28 |  |
| MT_STP_NOGROUP | 27 |  |
| MT_SHUTDOWN | 45 |  |
| MT_CONFIRM_SHUTDOWN | 50 |  |
| MT_RTMESSAGE0 | 30 |  |
| MT_RTMESSAGE1 | 31 |  |
| MT_RTMESSAGE2 | 32 |  |
| MT_RTMESSAGE3 | 33 |  |
| MT_RTMESSAGE4 | 34 |  |
| MT_ASCII | 100 |  |
| MT_UNICODE | 101 |  |
| MT_GCODE | 102 |  |
| MT_PYTHON | 103 |  |
| MT_PICKLE | 104 |  |
| MT_TCL | 105 |  |
| MT_XML | 106 |  |
| MT_JSON | 107 |  |
| MT_JPEG | 108 |  |
| MT_PNG | 109 |  |
| MT_TIFF | 110 |  |
| MT_POSTSCRIPT | 111 |  |
| MT_SVG | 112 |  |
| MT_ZMQ_SUBSCRIBE | 150 |  |
| MT_ZMQ_UNSUBSCRIBE | 151 |  |
| MT_PING | 210 |  |
| MT_PING_ACKNOWLEDGE | 215 |  |
| MT_REJECT | 220 |  |
| MT_DONE | 240 |  |
| MT_SERVICE_REQUEST | 250 |  |
| MT_SERVICE_ANNOUNCEMENT | 251 |  |
| MT_SERVICE_PROBE | 252 |  |
| MT_MESSAGEBUS_NO_DESTINATION | 255 |  |
| MT_HALRCOMP_BIND | 256 |  |
| MT_HALRCOMP_BIND_CONFIRM | 257 |  |
| MT_HALRCOMP_BIND_REJECT | 258 |  |
| MT_HALRCOMP_SET | 259 |  |
| MT_HALRCOMP_SET_REJECT | 260 |  |
| MT_HALRCOMP_ACK | 263 |  |
| MT_HALRCOMMAND_SET | 265 |  |
| MT_HALRCOMMAND_SET_REJECT | 266 |  |
| MT_HALRCOMMAND_GET | 267 |  |
| MT_HALRCOMMAND_GET_REJECT | 268 |  |
| MT_HALRCOMMAND_CREATE | 269 |  |
| MT_HALRCOMMAND_CREATE_REJECT | 270 |  |
| MT_HALRCOMMAND_DELETE | 271 |  |
| MT_HALRCOMMAND_DELETE_REJECT | 272 |  |
| MT_HALRCOMMAND_ACK | 273 |  |
| MT_HALRCOMMAND_ERROR | 274 |  |
| MT_HALRCOMMAND_DESCRIBE | 276 |  |
| MT_HALRCOMMAND_DESCRIPTION | 277 |  |
| MT_HALRCOMP_FULL_UPDATE | 288 |  |
| MT_HALRCOMP_INCREMENTAL_UPDATE | 289 |  |
| MT_HALRCOMP_ERROR | 290 |  |
| MT_HALGROUP_BIND | 294 |  |
| MT_HALGROUP_BIND_CONFIRM | 295 |  |
| MT_HALGROUP_BIND_REJECT | 296 |  |
| MT_HALGROUP_FULL_UPDATE | 297 |  |
| MT_HALGROUP_INCREMENTAL_UPDATE | 298 |  |
| MT_HALGROUP_ERROR | 299 |  |
| MT_RTAPI_APP_EXIT | 300 |  |
| MT_RTAPI_APP_PING | 301 |  |
| MT_RTAPI_APP_LOADRT | 302 |  |
| MT_RTAPI_APP_LOG | 303 |  |
| MT_RTAPI_APP_UNLOADRT | 305 |  |
| MT_RTAPI_APP_NEWINST | 306 |  |
| MT_RTAPI_APP_NEWTHREAD | 307 |  |
| MT_RTAPI_APP_DELTHREAD | 308 |  |
| MT_RTAPI_APP_CALLFUNC | 309 |  |
| MT_RTAPI_APP_REPLY | 310 |  |
| MT_RTAPI_APP_DELINST | 311 |  |
| MT_LIST_APPLICATIONS | 350 |  |
| MT_DESCRIBE_APPLICATION | 351 |  |
| MT_RETRIEVE_APPLICATION | 352 |  |
| MT_APPLICATION_DETAIL | 353 |  |
| MT_ERROR | 360 |  |
| MT_TASK_REPLY | 400 |  |
| MT_TICKET_UPDATE | 401 |  |
| MT_CREDIT_UPDATE | 450 |  |
| MT_EMCMOT_LOWER | 1000 |  |
| MT_EMCMOT_UPPER | 1100 |  |
| MT_EMCMOT_ABORT | 1001 |  |
| MT_EMCMOT_AXIS_ABORT | 1002 |  |
| MT_EMCMOT_ENABLE | 1003 |  |
| MT_EMCMOT_DISABLE | 1004 |  |
| MT_EMCMOT_ENABLE_AMPLIFIER | 1005 |  |
| MT_EMCMOT_DISABLE_AMPLIFIER | 1006 |  |
| MT_EMCMOT_ENABLE_WATCHDOG | 1007 |  |
| MT_EMCMOT_DISABLE_WATCHDOG | 1008 |  |
| MT_EMCMOT_ACTIVATE_JOINT | 1009 |  |
| MT_EMCMOT_DEACTIVATE_JOINT | 1010 |  |
| MT_EMCMOT_PAUSE | 1011 |  |
| MT_EMCMOT_RESUME | 1012 |  |
| MT_EMCMOT_STEP | 1013 |  |
| MT_EMCMOT_FREE | 1014 |  |
| MT_EMCMOT_COORD | 1015 |  |
| MT_EMCMOT_TELEOP | 1016 |  |
| MT_EMCMOT_SPINDLE_SCALE | 1017 |  |
| MT_EMCMOT_SS_ENABLE | 1018 |  |
| MT_EMCMOT_FEED_SCALE | 1019 |  |
| MT_EMCMOT_FS_ENABLE | 1020 |  |
| MT_EMCMOT_FH_ENABLE | 1021 |  |
| MT_EMCMOT_AF_ENABLE | 1022 |  |
| MT_EMCMOT_OVERRIDE_LIMITS | 1023 |  |
| MT_EMCMOT_HOME | 1024 |  |
| MT_EMCMOT_UNHOME | 1025 |  |
| MT_EMCMOT_JOG_CONT | 1026 |  |
| MT_EMCMOT_JOG_INCR | 1027 |  |
| MT_EMCMOT_JOG_ABS | 1028 |  |
| MT_EMCMOT_SET_LINE | 1029 |  |
| MT_EMCMOT_SET_CIRCLE | 1030 |  |
| MT_EMCMOT_SET_TELEOP_VECTOR | 1031 |  |
| MT_EMCMOT_CLEAR_PROBE_FLAGS | 1032 |  |
| MT_EMCMOT_PROBE | 1033 |  |
| MT_EMCMOT_RIGID_TAP | 1034 |  |
| MT_EMCMOT_SET_POSITION_LIMITS | 1035 |  |
| MT_EMCMOT_SET_BACKLASH | 1036 |  |
| MT_EMCMOT_SET_MIN_FERROR | 1037 |  |
| MT_EMCMOT_SET_MAX_FERROR | 1038 |  |
| MT_EMCMOT_SET_VEL | 1039 |  |
| MT_EMCMOT_SET_VEL_LIMIT | 1040 |  |
| MT_EMCMOT_SET_JOINT_VEL_LIMIT | 1041 |  |
| MT_EMCMOT_SET_JOINT_ACC_LIMIT | 1042 |  |
| MT_EMCMOT_SET_ACC | 1043 |  |
| MT_EMCMOT_SET_TERM_COND | 1044 |  |
| MT_EMCMOT_SET_NUM_AXES | 1045 |  |
| MT_EMCMOT_SET_WORLD_HOME | 1046 |  |
| MT_EMCMOT_SET_HOMING_PARAMS | 1047 |  |
| MT_EMCMOT_SET_DEBUG | 1048 |  |
| MT_EMCMOT_SET_DOUT | 1049 |  |
| MT_EMCMOT_SET_AOUT | 1050 |  |
| MT_EMCMOT_SET_SPINDLESYNC | 1051 |  |
| MT_EMCMOT_SPINDLE_ON | 1052 |  |
| MT_EMCMOT_SPINDLE_OFF | 1053 |  |
| MT_EMCMOT_SPINDLE_INCREASE | 1054 |  |
| MT_EMCMOT_SPINDLE_DECREASE | 1055 |  |
| MT_EMCMOT_SPINDLE_BRAKE_ENGAGE | 1056 |  |
| MT_EMCMOT_SPINDLE_BRAKE_RELEASE | 1057 |  |
| MT_EMCMOT_SET_MOTOR_OFFSET | 1058 |  |
| MT_EMCMOT_SET_JOINT_COMP | 1059 |  |
| MT_EMCMOT_SET_OFFSET | 1060 |  |
| MT_EMCMOT_COMMAND_OK | 1061 |  |
| MT_EMCMOT_COMMAND_UNKNOWN_COMMAND | 1062 |  |
| MT_EMCMOT_COMMAND_INVALID_COMMAND | 1063 |  |
| MT_EMCMOT_COMMAND_INVALID_PARAMS | 1064 |  |
| MT_EMCMOT_COMMAND_BAD_EXEC | 1065 |  |
| MT_EMCMOT_MOTION_DISABLED | 1066 |  |
| MT_EMCMOT_MOTION_FREE | 1067 |  |
| MT_EMCMOT_MOTION_TELEOP | 1068 |  |
| MT_EMCMOT_MOTION_COORD | 1069 |  |
| MT_EMCMOT_JOINT_FLAG | 1070 |  |
| MT_EMCMOT_MOTION_FLAG | 1071 |  |
| MT_PRU_FIRMWARE | 2048 |  |
| MT_MESA_5I20_FIRMWARE | 3000 |  |
| MT_BLOB | 4000 |  |
| MT_TEST1 | 5001 |  |
| MT_TEST2 | 5002 |  |
| MT_TEST3 | 5003 |  |
| MT_EMC_NML_LOWER | 10000 |  |
| MT_EMC_NML_UPPER | 13000 |  |
| MT_EMC_OPERATOR_ERROR | 10011 |  |
| MT_EMC_OPERATOR_TEXT | 10012 |  |
| MT_EMC_OPERATOR_DISPLAY | 10013 |  |
| MT_EMC_NULL | 10021 |  |
| MT_EMC_SET_DEBUG | 10022 |  |
| MT_EMC_SYSTEM_CMD | 10030 |  |
| MT_EMC_AXIS_SET_AXIS | 10101 |  |
| MT_EMC_AXIS_SET_UNITS | 10102 |  |
| MT_EMC_AXIS_SET_MIN_POSITION_LIMIT | 10107 |  |
| MT_EMC_AXIS_SET_MAX_POSITION_LIMIT | 10108 |  |
| MT_EMC_TOOL_START_CHANGE | 1110 |  |
| MT_EMC_EXEC_PLUGIN_CALL | 1112 |  |
| MT_EMC_IO_PLUGIN_CALL | 1113 |  |
| MT_EMC_AXIS_SET_FERROR | 10111 |  |
| MT_EMC_AXIS_SET_HOMING_PARAMS | 10112 |  |
| MT_EMC_AXIS_SET_MIN_FERROR | 10115 |  |
| MT_EMC_AXIS_SET_MAX_VELOCITY | 10116 |  |
| MT_EMC_AXIS_INIT | 10118 |  |
| MT_EMC_AXIS_HALT | 10119 |  |
| MT_EMC_AXIS_ABORT | 10120 |  |
| MT_EMC_AXIS_ENABLE | 10121 |  |
| MT_EMC_AXIS_DISABLE | 10122 |  |
| MT_EMC_AXIS_HOME | 10123 |  |
| MT_EMC_AXIS_UNHOME | 10135 |  |
| MT_EMC_AXIS_JOG | 10124 |  |
| MT_EMC_AXIS_INCR_JOG | 10125 |  |
| MT_EMC_AXIS_ABS_JOG | 10126 |  |
| MT_EMC_AXIS_ACTIVATE | 10127 |  |
| MT_EMC_AXIS_DEACTIVATE | 10128 |  |
| MT_EMC_AXIS_OVERRIDE_LIMITS | 10129 |  |
| MT_EMC_AXIS_LOAD_COMP | 10131 |  |
| MT_EMC_AXIS_SET_BACKLASH | 10134 |  |
| MT_EMC_AXIS_STAT | 10199 |  |
| MT_EMC_TRAJ_SET_AXES | 10201 |  |
| MT_EMC_TRAJ_SET_UNITS | 10202 |  |
| MT_EMC_TRAJ_SET_CYCLE_TIME | 10203 |  |
| MT_EMC_TRAJ_SET_MODE | 10204 |  |
| MT_EMC_TRAJ_SET_VELOCITY | 10205 |  |
| MT_EMC_TRAJ_SET_ACCELERATION | 10206 |  |
| MT_EMC_TRAJ_SET_MAX_VELOCITY | 10207 |  |
| MT_EMC_TRAJ_SET_MAX_ACCELERATION | 10208 |  |
| MT_EMC_TRAJ_SET_SCALE | 10209 |  |
| MT_EMC_TRAJ_SET_MOTION_ID | 10210 |  |
| MT_EMC_TRAJ_INIT | 10211 |  |
| MT_EMC_TRAJ_HALT | 10212 |  |
| MT_EMC_TRAJ_ENABLE | 10213 |  |
| MT_EMC_TRAJ_DISABLE | 10214 |  |
| MT_EMC_TRAJ_ABORT | 10215 |  |
| MT_EMC_TRAJ_PAUSE | 10216 |  |
| MT_EMC_TRAJ_STEP | 10217 |  |
| MT_EMC_TRAJ_RESUME | 10218 |  |
| MT_EMC_TRAJ_DELAY | 10219 |  |
| MT_EMC_TRAJ_LINEAR_MOVE | 10220 |  |
| MT_EMC_TRAJ_CIRCULAR_MOVE | 10221 |  |
| MT_EMC_TRAJ_SET_TERM_COND | 10222 |  |
| MT_EMC_TRAJ_SET_OFFSET | 10223 |  |
| MT_EMC_TRAJ_SET_G5X | 10224 |  |
| MT_EMC_TRAJ_SET_HOME | 10225 |  |
| MT_EMC_TRAJ_SET_ROTATION | 10226 |  |
| MT_EMC_TRAJ_SET_G92 | 10227 |  |
| MT_EMC_TRAJ_CLEAR_PROBE_TRIPPED_FLAG | 10228 |  |
| MT_EMC_TRAJ_PROBE | 10229 |  |
| MT_EMC_TRAJ_SET_TELEOP_ENABLE | 10230 |  |
| MT_EMC_TRAJ_SET_TELEOP_VECTOR | 10231 |  |
| MT_EMC_TRAJ_SET_SPINDLESYNC | 10232 |  |
| MT_EMC_TRAJ_SET_SPINDLE_SCALE | 10233 |  |
| MT_EMC_TRAJ_SET_FO_ENABLE | 10234 |  |
| MT_EMC_TRAJ_SET_SO_ENABLE | 10235 |  |
| MT_EMC_TRAJ_SET_FH_ENABLE | 10236 |  |
| MT_EMC_TRAJ_RIGID_TAP | 10237 |  |
| MT_EMC_TRAJ_STAT | 10299 |  |
| MT_EMC_MOTION_INIT | 10301 |  |
| MT_EMC_MOTION_HALT | 10302 |  |
| MT_EMC_MOTION_ABORT | 10303 |  |
| MT_EMC_MOTION_SET_AOUT | 10304 |  |
| MT_EMC_MOTION_SET_DOUT | 10305 |  |
| MT_EMC_MOTION_ADAPTIVE | 10306 |  |
| MT_EMC_SPINDLE_ORIENT | 10317 |  |
| MT_EMC_SPINDLE_WAIT_ORIENT_COMPLETE | 10318 |  |
| MT_EMC_MOTION_STAT | 10399 |  |
| MT_EMC_TASK_INIT | 10501 |  |
| MT_EMC_TASK_HALT | 10502 |  |
| MT_EMC_TASK_ABORT | 10503 |  |
| MT_EMC_TASK_SET_MODE | 10504 |  |
| MT_EMC_TASK_SET_STATE | 10505 |  |
| MT_EMC_TASK_PLAN_OPEN | 10506 |  |
| MT_EMC_TASK_PLAN_RUN | 10507 |  |
| MT_EMC_TASK_PLAN_READ | 10508 |  |
| MT_EMC_TASK_PLAN_EXECUTE | 10509 |  |
| MT_EMC_TASK_PLAN_PAUSE | 10510 |  |
| MT_EMC_TASK_PLAN_STEP | 10511 |  |
| MT_EMC_TASK_PLAN_RESUME | 10512 |  |
| MT_EMC_TASK_PLAN_END | 10513 |  |
| MT_EMC_TASK_PLAN_CLOSE | 10514 |  |
| MT_EMC_TASK_PLAN_INIT | 10515 |  |
| MT_EMC_TASK_PLAN_SYNCH | 10516 |  |
| MT_EMC_TASK_PLAN_SET_OPTIONAL_STOP | 10517 |  |
| MT_EMC_TASK_PLAN_SET_BLOCK_DELETE | 10518 |  |
| MT_EMC_TASK_PLAN_OPTIONAL_STOP | 10519 |  |
| MT_EMC_TASK_PLAN_RESET | 10520 |  |
| MT_EMC_TASK_PLAN_REPLY | 10530 |  |
| MT_EMC_TASK_STAT | 10599 |  |
| MT_EMC_TOOL_INIT | 11101 |  |
| MT_EMC_TOOL_HALT | 11102 |  |
| MT_EMC_TOOL_ABORT | 11103 |  |
| MT_EMC_TOOL_PREPARE | 11104 |  |
| MT_EMC_TOOL_LOAD | 11105 |  |
| MT_EMC_TOOL_UNLOAD | 11106 |  |
| MT_EMC_TOOL_LOAD_TOOL_TABLE | 11107 |  |
| MT_EMC_TOOL_SET_OFFSET | 11108 |  |
| MT_EMC_TOOL_SET_NUMBER | 11109 |  |
| MT_EMC_TOOL_STAT | 11199 |  |
| MT_EMC_AUX_ESTOP_ON | 11206 |  |
| MT_EMC_AUX_ESTOP_OFF | 11207 |  |
| MT_EMC_AUX_ESTOP_RESET | 11208 |  |
| MT_EMC_AUX_INPUT_WAIT | 11209 |  |
| MT_EMC_AUX_STAT | 11299 |  |
| MT_EMC_SPINDLE_ON | 11304 |  |
| MT_EMC_SPINDLE_OFF | 11305 |  |
| MT_EMC_SPINDLE_INCREASE | 11309 |  |
| MT_EMC_SPINDLE_DECREASE | 11310 |  |
| MT_EMC_SPINDLE_CONSTANT | 11311 |  |
| MT_EMC_SPINDLE_BRAKE_RELEASE | 11312 |  |
| MT_EMC_SPINDLE_BRAKE_ENGAGE | 11313 |  |
| MT_EMC_SPINDLE_SPEED | 11316 |  |
| MT_EMC_SPINDLE_STAT | 11399 |  |
| MT_EMC_COOLANT_MIST_ON | 11404 |  |
| MT_EMC_COOLANT_MIST_OFF | 11405 |  |
| MT_EMC_COOLANT_FLOOD_ON | 11406 |  |
| MT_EMC_COOLANT_FLOOD_OFF | 11407 |  |
| MT_EMC_COOLANT_STAT | 11499 |  |
| MT_EMC_LUBE_ON | 11504 |  |
| MT_EMC_LUBE_OFF | 11505 |  |
| MT_EMC_LUBE_STAT | 11599 |  |
| MT_EMC_IO_INIT | 11601 |  |
| MT_EMC_IO_HALT | 11602 |  |
| MT_EMC_IO_ABORT | 11603 |  |
| MT_EMC_IO_SET_CYCLE_TIME | 11604 |  |
| MT_EMC_IO_STAT | 11699 |  |
| MT_EMC_INIT | 11901 |  |
| MT_EMC_HALT | 11902 |  |
| MT_EMC_ABORT | 11903 |  |
| MT_EMC_STAT | 11999 |  |
| MT_EMCSTAT_FULL_UPDATE | 12500 |  |
| MT_EMCSTAT_INCREMENTAL_UPDATE | 12501 |  |
| MT_EMC_NML_ERROR | 12510 |  |
| MT_EMC_NML_TEXT | 12511 |  |
| MT_EMC_NML_DISPLAY | 12512 |  |
| MT_EMCCMD_EXECUTED | 12520 |  |
| MT_EMCCMD_COMPLETED | 12521 |  |
| MT_LAUNCHER_FULL_UPDATE | 12600 |  |
| MT_LAUNCHER_INCREMENTAL_UPDATE | 12601 |  |
| MT_LAUNCHER_ERROR | 12602 |  |
| MT_LAUNCHER_START | 12610 |  |
| MT_LAUNCHER_TERMINATE | 12611 |  |
| MT_LAUNCHER_KILL | 12612 |  |
| MT_LAUNCHER_WRITE_STDIN | 12613 |  |
| MT_LAUNCHER_CALL | 12614 |  |
| MT_LAUNCHER_SHUTDOWN | 12615 |  |
| MT_PARAM_FULL_UPDATE | 12700 |  |
| MT_PARAM_INCREMENTAL_UPDATE | 12701 |  |
| MT_PARAM_ERROR | 12702 |  |
| MT_PARAM_SET | 12710 |  |
| MT_PARAM_DELETE | 12711 |  |
| MT_FULL_UPDATE | 14000 |  |
| MT_INCREMENTAL_UPDATE | 14001 |  |

<a name="pb.HalParamDirection"/>
### HalParamDirection


| Name | Number | Description |
| ---- | ------ | ----------- |
| HAL_RO | 64 |  |
| HAL_RW | 192 |  |

<a name="pb.HalPinDirection"/>
### HalPinDirection


| Name | Number | Description |
| ---- | ------ | ----------- |
| HAL_IN | 16 |  |
| HAL_OUT | 32 |  |
| HAL_IO | 48 |  |

<a name="pb.InputType"/>
### InputType


| Name | Number | Description |
| ---- | ------ | ----------- |
| _ANALOG_INPUT | 0 |  |
| _DIGITAL_INPUT | 1 |  |

<a name="pb.InterpreterStateType"/>
### InterpreterStateType


| Name | Number | Description |
| ---- | ------ | ----------- |
| INTERP_IDLE | 1 |  |
| INTERP_RUNNING | 2 |  |
| INTERP_SYNC_WAIT | 3 |  |
| INTERP_PAUSED | 4 |  |
| INTERP_QUEUE_WAIT | 5 |  |
| INTERP_ABORT_WAIT | 6 |  |
| INTERP_STATE_UNSET | 99 |  |

<a name="pb.MsgLevel"/>
### MsgLevel


| Name | Number | Description |
| ---- | ------ | ----------- |
| RTAPI_MSG_NONE | 0 |  |
| RTAPI_MSG_ERR | 1 |  |
| RTAPI_MSG_WARN | 2 |  |
| RTAPI_MSG_INFO | 3 |  |
| RTAPI_MSG_DBG | 4 |  |
| RTAPI_MSG_ALL | 5 |  |

<a name="pb.MsgOrigin"/>
### MsgOrigin


| Name | Number | Description |
| ---- | ------ | ----------- |
| MSG_KERNEL | 0 |  |
| MSG_RTUSER | 1 |  |
| MSG_ULAPI | 2 |  |

<a name="pb.ObjectType"/>
### ObjectType


| Name | Number | Description |
| ---- | ------ | ----------- |
| HAL_PIN | 1 |  |
| HAL_SIGNAL | 2 |  |
| HAL_PARAM | 3 |  |
| HAL_THREAD | 4 |  |
| HAL_FUNCT | 5 |  |
| HAL_ALIAS | 6 |  |
| HAL_COMP_RT | 7 |  |
| HAL_COMP_USER | 8 |  |
| HAL_COMP_REMOTE | 9 |  |
| HAL_RING | 10 |  |
| HAL_GROUP | 11 |  |
| HAL_MEMBER_SIGNAL | 12 |  |
| HAL_MEMBER_GROUP | 13 |  |
| HAL_MEMBER_PIN | 14 |  |
| HAL_MEMBER_PARAM | 15 |  |
| RING_RECORD | 16 |  |
| RING_STREAM | 17 |  |
| HAL_VTABLE | 18 |  |
| HAL_INST | 19 |  |
| RING_MULTIFRAME | 20 |  |
| VALUE | 120 |  |
| INSTANCE | 121 |  |
| ORIGINATOR | 122 |  |
| NAMED_VALUE | 125 |  |
| OT_ERROR | 130 |  |

<a name="pb.OriginDetail"/>
### OriginDetail


| Name | Number | Description |
| ---- | ------ | ----------- |
| UNIX_SIGNAL | 10 |  |
| INSTANCE_SHUTDOWN | 20 |  |
| ZMQ_SOCKET | 70 |  |
| NML_LAYER | 80 |  |
| RCS_LAYER | 90 |  |
| CMS_LAYER | 100 |  |
| IP_LAYER | 110 |  |
| TCP_LAYER | 120 |  |
| PGM_LAYER | 130 |  |

<a name="pb.OriginIndex"/>
### OriginIndex


| Name | Number | Description |
| ---- | ------ | ----------- |
| ORIGIN_UNKNOWN | 0 |  |
| ORIGIN_G54 | 1 |  |
| ORIGIN_G55 | 2 |  |
| ORIGIN_G56 | 3 |  |
| ORIGIN_G57 | 4 |  |
| ORIGIN_G58 | 5 |  |
| ORIGIN_G59 | 6 |  |
| ORIGIN_G59_1 | 7 |  |
| ORIGIN_G59_2 | 8 |  |
| ORIGIN_G59_3 | 9 |  |

<a name="pb.OriginType"/>
### OriginType


| Name | Number | Description |
| ---- | ------ | ----------- |
| PROCESS | 10 |  |
| USER_THREAD | 20 |  |
| RT_THREAD | 30 |  |
| COMPONENT | 40 |  |
| THREAD_FUNCTION | 50 |  |
| COMPONENT_INIT | 60 |  |
| COMPONENT_EXIT | 70 |  |
| GROUP | 80 |  |
| PIN | 90 |  |
| SIGNAL | 100 |  |

<a name="pb.RCS_STATUS"/>
### RCS_STATUS


| Name | Number | Description |
| ---- | ------ | ----------- |
| UNINITIALIZED_STATUS | -1 |  |
| RCS_DONE | 1 |  |
| RCS_EXEC | 2 |  |
| RCS_ERROR | 3 |  |
| RCS_RECEIVED | 4 |  |

<a name="pb.ReplyType"/>
### ReplyType


| Name | Number | Description |
| ---- | ------ | ----------- |
| NONE | 0 |  |
| ON_RECEPTION | 1 |  |
| ON_QUEUED | 2 |  |
| ON_COMPLETION | 4 |  |
| ALL_STEPS | 255 |  |

<a name="pb.ServiceAPI"/>
### ServiceAPI


| Name | Number | Description |
| ---- | ------ | ----------- |
| SA_ZMQ_PROTOBUF | 1 |  |
| SA_WS_JSON | 2 |  |

<a name="pb.ServiceType"/>
### ServiceType


| Name | Number | Description |
| ---- | ------ | ----------- |
| ST_LOGGING | 1 |  |
| ST_CONFIG | 2 |  |
| ST_REDIS | 3 |  |
| ST_HTTP | 4 |  |
| ST_HTTPS | 5 |  |
| ST_WEBSOCKET | 6 |  |
| ST_WEBSOCKETS | 7 |  |
| ST_RTAPI_COMMAND | 8 |  |
| ST_STP_HALGROUP | 9 |  |
| ST_STP_HALRCOMP | 10 |  |
| ST_STP_INTERP | 11 |  |
| ST_STP_TASK | 12 |  |
| ST_HAL_RCOMMAND | 13 |  |
| ST_TASK_COMMAND | 14 |  |
| ST_INTERP_COMMAND | 15 |  |
| ST_MESSAGEBUS_COMMAND | 16 |  |
| ST_MESSAGEBUS_RESPONSE | 17 |  |

<a name="pb.Severity"/>
### Severity


| Name | Number | Description |
| ---- | ------ | ----------- |
| S_INFORMATIONAL | 1 |  |
| S_WARNING | 2 |  |
| S_FAIL | 4 |  |

<a name="pb.StatusType"/>
### StatusType


| Name | Number | Description |
| ---- | ------ | ----------- |
| ENQUEUED | 1 |  |
| PROCESSING | 2 |  |
| COMPLETE | 3 |  |
| FAILED | 4 |  |

<a name="pb.TermConditionType"/>
### TermConditionType


| Name | Number | Description |
| ---- | ------ | ----------- |
| _EMC_TRAJ_TERM_COND_STOP | 1 |  |
| _EMC_TRAJ_TERM_COND_BLEND | 2 |  |

<a name="pb.ValueType"/>
### ValueType


| Name | Number | Description |
| ---- | ------ | ----------- |
| HAL_BIT | 1 |  |
| HAL_FLOAT | 2 |  |
| HAL_S32 | 3 |  |
| HAL_U32 | 4 |  |
| STRING | 5 |  |
| BYTES | 6 |  |
| INT32 | 20 |  |
| UINT32 | 30 |  |
| INT64 | 40 |  |
| UINT64 | 50 |  |
| DOUBLE | 60 |  |
| BOOL | 80 |  |
| CARTESIAN | 100 |  |
| LEGACY_CARTESIAN | 110 |  |
| POSE | 120 |  |
| LEGACY_POSE | 130 |  |

<a name="pb.WaitType"/>
### WaitType


| Name | Number | Description |
| ---- | ------ | ----------- |
| IMMEDIATE | 0 |  |
| RISE | 1 |  |
| FALL | 2 |  |
| BE_HIGH | 3 |  |
| BE_LOW | 4 |  |

<a name="value.proto"/>
<p align="right"><a href="#top">Top</a></p>

## value.proto

<a name="pb.Value"/>
### Value


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| <a name="pb.Value.type"/> type | [ValueType](#pb.ValueType) | required |  |
| <a name="pb.Value.halbit"/> halbit | [bool](#bool) | optional |  |
| <a name="pb.Value.halfloat"/> halfloat | [double](#double) | optional |  |
| <a name="pb.Value.hals32"/> hals32 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Value.halu32"/> halu32 | [fixed32](#fixed32) | optional |  |
| <a name="pb.Value.v_bytes"/> v_bytes | [bytes](#bytes) | optional |  |
| <a name="pb.Value.v_int32"/> v_int32 | [sfixed32](#sfixed32) | optional |  |
| <a name="pb.Value.v_int64"/> v_int64 | [sfixed64](#sfixed64) | optional |  |
| <a name="pb.Value.v_uint32"/> v_uint32 | [fixed32](#fixed32) | optional |  |
| <a name="pb.Value.v_uint64"/> v_uint64 | [fixed64](#fixed64) | optional |  |
| <a name="pb.Value.v_double"/> v_double | [double](#double) | optional |  |
| <a name="pb.Value.v_string"/> v_string | [string](#string) | optional |  |
| <a name="pb.Value.v_bool"/> v_bool | [bool](#bool) | optional |  |
| <a name="pb.Value.carte"/> carte | [PmCartesian](#pb.PmCartesian) | optional |  |
| <a name="pb.Value.pose"/> pose | [EmcPose](#pb.EmcPose) | optional |  |



<a name="scalar-value-types"/>
## Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <a name="double"/> double |  | double | double | float |
| <a name="float"/> float |  | float | float | float |
| <a name="int32"/> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <a name="int64"/> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <a name="uint32"/> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <a name="uint64"/> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <a name="sint32"/> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <a name="sint64"/> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <a name="fixed32"/> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <a name="fixed64"/> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <a name="sfixed32"/> sfixed32 | Always four bytes. | int32 | int | int |
| <a name="sfixed64"/> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <a name="bool"/> bool |  | bool | boolean | boolean |
| <a name="string"/> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <a name="bytes"/> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |
