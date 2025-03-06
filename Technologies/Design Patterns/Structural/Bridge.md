---
tags:
---
Date: 2025-03-06 : 14:44
***
## Intent
Helps to split a large class or a set of closely related classes into different two different ones, which are **abstraction and implementation**.

The **abstraction** is the logic and relies on the implementation. We can say it is the API.

The **implementation** is an interface for all the implementations. We can say it is the GUI.

## Structure
![[structure-bridge.png]]

## Code Example
```go
// Device is the implementation interface.
// It defines operations that concrete devices (TV, Radio) must implement.
type Device interface {
	TurnOn()
	TurnOff()
	SetVolume(volume int)
}

// TV is a concrete implementation of Device.
type TV struct {
	volume int
	on     bool
}

func (tv *TV) TurnOn() {
	tv.on = true
	fmt.Println("TV is turned on")
}

func (tv *TV) TurnOff() {
	tv.on = false
	fmt.Println("TV is turned off")
}

func (tv *TV) SetVolume(volume int) {
	tv.volume = volume
	fmt.Printf("TV volume set to %d\n", volume)
}

// Radio is another concrete implementation of Device.
type Radio struct {
	volume int
	on     bool
}

func (r *Radio) TurnOn() {
	r.on = true
	fmt.Println("Radio is turned on")
}

func (r *Radio) TurnOff() {
	r.on = false
	fmt.Println("Radio is turned off")
}

func (r *Radio) SetVolume(volume int) {
	r.volume = volume
	fmt.Printf("Radio volume set to %d\n", volume)
}

// Remote is the abstraction. It holds a reference to a Device,
// allowing the remote to work with any concrete implementation.
type Remote struct {
	device Device
}

func (r *Remote) TogglePower() {
	// In a real-world scenario, you'd check the current state of the device.
	fmt.Println("Remote toggles power:")
	r.device.TurnOn()
}

func (r *Remote) SetVolume(volume int) {
	r.device.SetVolume(volume)
}

// AdvancedRemote extends Remote with additional functionality.
type AdvancedRemote struct {
	*Remote // Embedding Remote to reuse its functionality
}

func (ar *AdvancedRemote) Mute() {
	fmt.Println("AdvancedRemote mutes the device:")
	ar.device.SetVolume(0)
}

func main() {
	// Use the basic Remote with a TV.
	tv := &TV{}
	remote := &Remote{device: tv}
	remote.TogglePower()
	remote.SetVolume(15)

	// Use the AdvancedRemote with a Radio.
	radio := &Radio{}
	advancedRemote := &AdvancedRemote{Remote: &Remote{device: radio}}
	advancedRemote.TogglePower()
	advancedRemote.SetVolume(7)
	advancedRemote.Mute()
}
```