Surface Reconstruction from Point Clouds (Colab)

Reconstruct meshes from .pcd/.ply/.xyz point clouds in Google Colab using Open3D. Supports Poisson and Ball-Pivoting, normals estimation, optional downsampling, density-based trimming, and mesh decimation. Exports .ply/.stl/.obj (and tries .glb).

Quick Start

Open PCD_Surface_Reconstruction_Open3D.ipynb in Colab.

Run 🔧 Setup.

Run ⬆️ Upload and select your point cloud.

Adjust ⚙️ Parameters (start with VOXEL_SIZE=0.01, POISSON_DEPTH=10).

Run either 🌀 Poisson or ⚽ Ball-Pivoting.

Use 💾 Download or the left file browser to fetch results.

Key Parameters

VOXEL_SIZE: pre-downsample spacing (↑ for speed, ↓ for detail).

NORMAL_RADIUS, NORMAL_MAX_NN: normal estimation.

POISSON_DEPTH (8–12 typical), POISSON_SCALE, DENSITY_TRIM_QUANTILE (0.01–0.05).

BP_RADII_SCALES: radii = scales × avg NN distance.

TARGET_TRIS: decimate to target triangle count (0 = off).

Outputs

Meshes: <name>_poisson.*, <name>_ballpivot.* (ply/stl/obj + optional glb).

Optional snapshots: pointcloud.png, mesh_poisson.png, mesh_ballpivot.png.

Troubleshooting

Kernel restarts / eglInitialize failed: comment out the render_snapshot(...) lines in the reconstruction cells (PNG previews only).

Large/Noisy clouds: increase VOXEL_SIZE, reduce POISSON_DEPTH, or raise NORMAL_RADIUS.

Oversmoothed mesh: lower VOXEL_SIZE or raise POISSON_DEPTH.
