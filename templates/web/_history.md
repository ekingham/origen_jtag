<a class="anchor release_tag" name="v0_11_0_pre5"></a>
<h2><a href="#v0_11_0_pre5">Tag: v0.11.0.pre5</a></h2>

##### Branch: 'Trunk'

##### by Corey Engelken on 12-Jun-2015 16:17PM


Added an 'arm\_debug\_comment' option that will be printed in the pattern just before the
data is shifted in. Small bugfix for arm\_debug\_overlays.

<a class="anchor release_tag" name="v0_11_0_pre4"></a>
<h2><a href="#v0_11_0_pre4">Tag: v0.11.0.pre4</a></h2>

##### Branch: 'Trunk'

##### by Corey Engelken on 21-May-2015 09:13AM


Added an additional check-for-not-fixnum during arm-debug overlays. Updated gemspec to use
newer version of Origen (was pre48).

<a class="anchor release_tag" name="v0_11_0_pre3"></a>
<h2><a href="#v0_11_0_pre3">Tag: v0.11.0.pre3</a></h2>

##### Branch: 'Trunk'

##### by Jiang Liu on 12-Feb-2015 20:49PM


patched in the 3 lines of overlay code that was supposed to be updated in the previous
patch.

<a class="anchor release_tag" name="v0_11_0_pre2"></a>
<h2><a href="#v0_11_0_pre2">Tag: v0.11.0.pre2</a></h2>

##### Branch: 'Trunk'

##### by Jiang Liu on 06-Feb-2015 16:43PM


Based on discussion with Corey, updated previously known as options[:overlay] to
options[:arm\_debug\_overlay], this
is causing a naming conflict between arm\_debug and nexus. This is just a temporary
workaround for everyone, in the future
this will be reworked.

<a class="anchor release_tag" name="v0_11_0_pre1"></a>
<h2><a href="#v0_11_0_pre1">Tag: v0.11.0.pre1</a></h2>

##### Branch: 'Trunk'

##### by Jiang Liu on 06-Feb-2015 11:52AM


add addtional overlay options for write\_dr method

<a class="anchor release_tag" name="v0_11_0_pre0"></a>
<h2><a href="#v0_11_0_pre0">Tag: v0.11.0.pre0</a></h2>

##### Branch: 'Trunk'

##### by Corey Engelken on 30-Dec-2014 11:41AM


Added options to enable arm-debug (which tears apart the registers) to correctly use
overlays and asserts (from reads).

<a class="anchor release_tag" name="v0_10_1"></a>
<h1><a href="#v0_10_1">Tag: v0.10.1</a></h1>

##### Branch: 'Trunk'

##### by Daniel Hadad on 11-Dec-2014 14:02PM


Rename gem to 'origen\_jtag' as there were conflicts with public gem named
'jtag'.
Added code (commented out) to permit using local/unreleased gem.
Updated to support origen\_core v2.5.0.pre18.


<a class="anchor release_tag" name="v0_10_0"></a>
<h1><a href="#v0_10_0">Tag: v0.10.0</a></h1>

##### Branch: 'Trunk'

##### by Daniel Hadad on 05-Dec-2014 14:15PM


Updated to be a gem, per origen 2.4.0 upgrade.

<a class="anchor release_tag" name="v0_9_2"></a>
<h1><a href="#v0_9_2">Tag: v0.9.2</a></h1>

##### Branch: 'Trunk'

##### by Stephen McGinty on 13-Nov-2014 06:37AM


Bug fix:
If an application disabled compares on TDO ($tester.ignore\_fails($dut.pin(:tdo) do..)
then this was not implemented by the JTAG driver and in fact it would actually remove the
suspend on that pin that had been set by the application.

Added test case for this and the necessary patch to fix it.

<a class="anchor release_tag" name="v0_9_1"></a>
<h1><a href="#v0_9_1">Tag: v0.9.1</a></h1>

##### Branch: 'Trunk'

##### by Stephen McGinty on 18-Aug-2014 08:38AM


Made the options argument to Driver#read\_dr and Driver#read\_ir optional as is the case with
the equivalent write methods.

Bumped the min Origen version to pick up a fix for an error caused by bit index references
to bits that are not present. i.e. on some Origen versions reg[10] where 10 does not exist
will raise an error whereas this driver is coded to expect it to return nil.

<a class="anchor release_tag" name="v0_9_0_dev0"></a>
<h2><a href="#v0_9_0_dev0">Tag: v0.9.0.dev0</a></h2>

##### Branch: 'Trunk'

##### by Yingpeng Kang on 30-Jun-2014 16:26PM


Added accessor tclk\_format

<a class="anchor release_tag" name="v0_9_0"></a>
<h1><a href="#v0_9_0">Tag: v0.9.0</a></h1>

##### Branch: 'Trunk'

##### by Daniel Hadad on 14-Mar-2014 17:07PM



Added tdo\_store\_cycle JTAG\_CONFIG option to permit specifying which vector to
store in multi-cycle TCK format.

<a class="anchor release_tag" name="v0_8_0"></a>
<h1><a href="#v0_8_0">Tag: v0.8.0</a></h1>

##### Branch: 'Trunk'

##### by Daniel Hadad on 24-Feb-2014 17:01PM


Added tdo\_strobe JTAG\_CONFIG option to permit only strobing TDO when TCK is high for
when TCK is greater than 1 tester cycle.  Options also include when TCK is low and
for all cycles of TCK.

<a class="anchor release_tag" name="v0_7_1"></a>
<h1><a href="#v0_7_1">Tag: v0.7.1</a></h1>

##### Branch: 'Trunk'

##### by Daniel Hadad on 20-Feb-2014 15:41PM


Corrected JTAG shift method to use TCK formatting properly.

<a class="anchor release_tag" name="v0_7_0"></a>
<h1><a href="#v0_7_0">Tag: v0.7.0</a></h1>

##### Branch: 'Trunk'

##### by Daniel Hadad on 19-Feb-2014 11:53AM


Added ability to modify TCLK timing format and the # of cycles TCLK spans for
cases where TCLK needs to run at a fraction of another clock pin.

Assumes 50% duty cycle.

To use update JTAG\_CONFIG in DUT model, e.g.

~~~ruby
  JTAG\_CONFIG = {
    :tclk\_format => :rl,
    :tclk\_multiple => 4
  }
~~~

Default is tclk\_format = :rh and tclk\_multiple = 1

<a class="anchor release_tag" name="v0_6_1"></a>
<h1><a href="#v0_6_1">Tag: v0.6.1</a></h1>

##### Branch: 'Trunk'

##### by Stephen McGinty on 19-Feb-2014 02:55AM


Fixed cases of driving/asserting nil values on a pin which latest Origen doesn't like.

Added release validation (ensure tests pass).

<a class="anchor release_tag" name="v0_6_0"></a>
<h1><a href="#v0_6_0">Tag: v0.6.0</a></h1>

##### Branch: 'Trunk'

##### by Stephen McGinty on 18-Dec-2013 08:31AM


Added integration with a tester supporting JTAG. If the tester model provides
read/write\_dr/ir methods then these will be deferred to to handle the requested
actions.

In short this means that any apps using a JTAG-based protocol can generate protocol
aware or bench patterns by simply using a tester model that implements these methods.

# Tag: v0.5.1

##### Branch: 'Trunk'

##### by Stephen McGinty on 02-Sep-2013 09:44AM


Bug fix to remove extra vector in a shift sequence when a full-width register is
overlaid.

# Tag: v0.5.0

##### Branch: 'Trunk'

##### by Daniel Hadad on 28-Aug-2013 17:16PM


Added reset method to tap controller.
Can pass message as option to read/write\_ir/dr methods that gets put as comment in pattern.

# Tag: v0.4.0

##### Branch: 'Trunk'

##### by Stephen McGinty on 28-Aug-2013 06:28AM


Can now accept Origen::Registers::Container instances in place of regular register
objects.

# Tag: v0.3.0

##### Branch: 'Trunk'

##### by Stephen McGinty on 22-Aug-2013 06:16AM


Added min/max Origen versions in place of fixed version. This should not have to change for
a long time unless a dependency on a future Origen is added.

# Tag: v0.2.0

##### Branch: 'Trunk'

##### by Stephen McGinty on 21-Aug-2013 09:24AM


Overlay bits will now be generated in-line rather than generating sub-routine calls
whenever Origen.mode.simulation? is true.

Added tracking of the IR register value and vectors from repeated calls to the write\_ir
method with the same value will now be inhibited.
Originally it was envisaged that higher level wrappers would take care of this but on
reflection this is probably not viable since there may be multiple protocols using the
same physical JTAG and therefore it is better tracked at the lowest level.

This change means that higher level libraries can pre-fix all of their operations
with a write to the IR with the value they need and the JTAG driver will take care of
keeping the vectors optimal.

This version depends on Origen >= v2.0.1.dev98.

# Tag: v0.1.0

##### Branch: 'Trunk'

##### by Stephen McGinty on 12-Aug-2013 06:31AM


Major API update and internal simplification. Removed all local tracking of IR and DR
registers states, that should be done by higher level wrappers.
See here for full details of the new API: http://origen.freescale.net/jtag

## Tag: v0.0.0.dev1

##### Branch: 'Trunk'

##### by Stephen McGinty on 09-Jul-2013 05:15AM


Removed illegal references to global objects ($soc, $tester, etc.) and added check that
the parent implements the required pins.

## Tag: v0.0.0.dev0

##### Branch: 'Trunk'

##### by Stephen McGinty on 03-Jul-2013 08:29AM


Initial version, extracted from C90TFS NVM app, probably doesn't work

