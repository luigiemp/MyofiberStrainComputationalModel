---------------------------------------------------------------------------------------------------
This supplementary dataset contains the model data for the subjects presented in Perotti et al.
If you have any questions or concerns, please contact Luigi Perotti (luigi.perotti@ucf.edu) and Ilya Verzhbinsky (iverzhbi@health.ucsd.edu).
----------------------------------------------------------------------------------------------------  

All subject folders contain the following files:

o   'S#.node' - contains all left ventricle mesh nodes in N x 3 format, where N is the number of mesh 
    nodes and 3 are the cartesian coordinates of the nodes. The header contains the number of nodes 
    followed by the dimension (i.e, 3 or 2 D) 

o   'S#.ele' - contains the connectivity table for the left ventricle finite elements in N x 8 format,
    where N is the number of elements and 8 corresponds to the number of nodal ID per element. Node numbering 
    starts at 0. The header of the file contains the number of elements followed by the Abaqus element type 
    (e.g., C3D8). 

o   'S#_invivo.Fiber' - contains the microstructure at all mesh quadrature points interpolated from 
    invivo DTMRI data in N x 9 format, where N is the number of quadrature points and 9 are the normalized components
    of the 3 eigenvectors of the diffusion tensor. The first 3 columns correspond to the primary eigenvector 
    (i.e., local aggregate cardiomyocyte orientation or myofiber), the next 3 columns correspond to the secondary eigenvector,
    and the last 3 columns correspond to the tertiary eigenvector

o   'S#_exvivo.Fiber' - contains the microstructure at all mesh quadrature points interpolated from 
    exvivo DTMRI data. The format is identical to the in vivo file described above. 
 
o   'S#.DENSE' - contains the left ventricle deformation mapping obtained from DENSE MRI and rigidly registered with
    the finite element model in the reference configuration. The grid-like nodes are organized in (N*3) x t format, 
    where N is the number of DENSE nodes and t is the number of imaged cardiac phases. Each set of 3 rows contains the 
    cartesian (x y z) coordinates of a single DENSE node through time.

o   'S#.BottomNodeSet' - contains the ID of all nodes on the most apical face (bottom) of the left ventricular mesh. Numbering 
    starts at 0. The first line of the file indicates how many nodes are in the set.

o   'S#.BottomEleSet' - contains the connectivity of all quadrilateral surface elements on the most apical (bottom) face 
    of the left ventricular mesh. Numbering starts at 0. The first line of the file indicates how many elements 
    are in the set, followed by the Abaqus element type (e.g., Q4).

o   'S#.TopNodeSet' - contains the ID of all nodes on the most basal (top) surface of the left ventricular mesh. Numbering 
    starts at 0. The first line of the file indicates how many nodes are in the set.

o   'S#.TopEleSet' - contains the connectivity of all quadrilateral surface elements on the most basal (top) surface of the 
    left ventricular mesh. Numbering starts at 0. The first line of the file indicates how many elements 
    are in the set, followed by the Abaqus element type (e.g., Q4).

o   'S#.EpiNodeSet' - contains the ID of all nodes on the epicardial (outer) surface of the left ventricular 
    mesh. Numbering starts at 0. The first line of the file indicates how many nodes are in the set.

o   'S#.EpiEleSet' - contains the connectivity of all quadrilateral surface elements on the epicardial (outer) surface 
    of left ventricular mesh. Numbering starts at 0. The first line of the file indicates how many elements are in the set, 
    followed by the Abaqus element type (e.g., Q4).

o   'S#.BoundaryCond' - contains the essential boundary condition in N x 2 format, where N is number of constrained dof.
    The first column lists the ID of the constrained nodes. The second column lists the constrained nodal dof (0, 1, and 2 
    correspond to constraining the node in the X, Y, and Z direction, respectively)

o   'DENSEdicoms' - is a subfolder containing the 3 DENSE midventricular slices used to generate the LV model geometry and the 
    ground truth deformation mapping. All DENSE data was processed using the DENSEanalysis tool, which can be 
    found at https://github.com/denseanalysis/denseanalysis.





